---
title:  "Pyinstaller 설치 시 오류"
search: false
categories: 
  - Software
tags:
  - Python
---

> Failed to import module __PyInstaller_hooks_0_numpy_core required by hook for module

아무 생각없이 작성한 파이썬 코드를 Pyinstaller를 이용해 실행파일로 만들려고 하니 에러가 발생.
해결책은 pip을 이용해서 numpy를 재설치해야한다.

```shell
pip install --upgrade --force-reinstall numpy
```
