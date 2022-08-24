---
title:  "MFC List box를 이용한 Log 남기기"
search: false
categories: 
  - Software
tags:
  - MFC
---
GUI 프로그램을 작성하다보면 직관적인 콘솔 프로그램에 비해 기록이 많이 남지 않는다는 단점이 있다. 물론 코드 작성 시에는 디버깅을 이용해서 각 단계 별로 코드가 어떻게 진행되는지 확인할 수 있지만, 실제 동작 시에 어떤 동작을 했는지 확인하기 위해서는 로그를 습관적으로 남기는 것이 중요하다. 파일로 남기는 로그도 중요하지만 MFC GUI 상에 로그를 남기는 방법도 사용할 수 있는데 단순 Edit control이나, list box에 차례대로 한 줄 씩 넘기면서 기록하는 것도 하나의 방법이다.

다만 MFC의 메시지를 사용하여 손쉽게 타임스탬프와 함께 로그를 남길 수 있는 방법이 가장 유용하다.

```c++
LRESULT CApplicationDlg::MsgStatus(WPARAM wParam, LPARAM lParam)
{
	LPCTSTR szMsg = (LPCTSTR)wParam;

	SYSTEMTIME systemTime;
	::GetLocalTime(&systemTime);
	CString strMsg;
	//로그가 남는 시간을 ms 단위까지 기록
	strMsg.Format(_T("%02d%02d%02d %02d:%02d:%02d:%03d> %s"), systemTime.wYear % 100, systemTime.wMonth, systemTime.wDay, systemTime.wHour, systemTime.wMinute, systemTime.wSecond, systemTime.wMilliseconds,
		szMsg);
	//m_OutputMSG는 ListBox 멤버변수
	m_OutputMSG.InsertString(0, strMsg);

	if (m_OutputMSG.GetCount() > 1000)
	{
		m_OutputMSG.DeleteString(1000); //1000줄이 넘어가면 오래된 것부터 지운다
	}

	return LRESULT(1);
}

void CApplicationDlg::AddMsg(LPCTSTR szMsg) // Message Display 함수
{
	SendMessage(UM_DISPLAY_MSG, (WPARAM)szMsg, NULL);
}

```

위 두 함수가 기본적으로 필요. 여기서는 연도를 두 자리만 표기하기 위해 systemTime.wYear%100 을 사용했다..

UM_DISPLAY_MSG 는 stdafx.h 또는 pch.h(미리 컴파일된 헤더)에 새롭게 작성하면 된다.
```C++
UM_DISPLAY_MSG
```

이제까지 작성한 부분은 임의의 함수를 만들기만 했고, 실제 메시지맵에 등록이 필요하다.
```C++
BEGIN_MESSAGE_MAP(CApplicationDlg, CDialogEx)
	ON_MESSAGE(UM_DISPLAY_MSG, &CApplicationDlg::MsgStatus)
END_MESSAGE_MAP()
```

등록까지 완료했으면, 실제함수는 AddMsg의 매개변수에 문자열을 넣으면 된다.
```C++
AddMsg(_T("Internet Connection confirmed.."));
```


완료, 주요 동작 지점마다 AddMsg를 이용하여 프로그램 사용 중에도 어떤 동작 순서를 가지고 있는지 확인이 가능하다.

<p align="center">
	<img width="460" height="300" data-action="zoom" src= "/assets/MyImages/2022-08-24(1).png" >
</p>
