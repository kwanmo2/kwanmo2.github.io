---
layout: default
title: e Ink dashboard 준비
parent: e Ink dashboard
grand_parent: 2021
nav_order: 1
---

# E ink dashboard 준비
## 준비물
- [X] Raspberry pi 3 or 4
- [X] waveshare epaper 7in5b\_HD(Black, Red color)\\

[\### Raspberry pi 3 or 4][1]
3이나 4, zero도 상관없다. 어차피 구현하려는 기능은 연산이 필요한 건 아니라 성능에 큰 영향을 받지 않는다. 파이썬이 돌아가고, e잉크 디스플레이 드라이버만 돌아가면 된다. 라즈비안 OS가 올라갈 SD카드도 4GB면 충분하다. 성능 좋은 라즈베리파이 4보다는 구형 라즈베리파이 2, 3 제품이 남아있다면 가장 적합하다. 

[\### waveshare epaper 7in5b\_HD(Black, Red color)][2]
- 알리바바에서 팔고 있는 대부분의 eInk 디스플레이는 waveshare라는 회사에서 제조한 제품이다. 가격도 그렇게 나쁘지 않아서 이 회사 제품으로 구매했다.
- 항상 이런 제품을 구매할 때는 깃헙이나 다른 예제들이 어떤 제품을 쓰고 있는지 미리 확인해보면 좋다.
- 많은 e-ink 대쉬보드 코드가 waveshare 디스플레이를 사용하고 있기에 망설임 없이 골랐다.
- 다양한 사이즈가 있는데 달력 내용을 잘 볼 수 있는 7인치 제품으로 골랐다

[\### 디스플레이 케이스][3]
- 7.5인치 디스플레이를 넣을 적당한 케이스를 알고 있다면 구매하지 않아도 괜찮다.
- 공대 감성이 좋다면 케이스가 없는 것도 좋다.
- 하지만 벽에 붙이거나 어딘가에 고정할 때 케이스가 있는 편이 좋다.

[\### 코드][4]
Mendhak라는 분이 작성한 코드를 바탕으로 [포킹][5]하여 사용할 예정이다. 같은 waveshare 7.5인치 제품이라고 하더라도, 컬러인지, 그리고 버전이 어떤지에 따라 불러올 라이브러리가 다르다. 이분이 작성한 [**블로그 페이지**][6]를 보고 원래 생각하던 e잉크 캘린더와 가장 유사한 이미지라 해당 코드를 채택했다.
 

[1]:	https://www.devicemart.co.kr/goods/view?no=1289629
[2]:	https://ko.aliexpress.com/item/4001142299891.html?gatewayAdapt=glo2kor&spm=a2g0o.9042311.0.0.27424c4dJMKiX6
[3]:	https://ko.aliexpress.com/item/32990539479.html?gatewayAdapt=glo2kor&spm=a2g0o.9042311.0.0.27424c4dJMKiX6
[4]:	https://github.com/mendhak/waveshare-epaper-display
[5]:	https://github.com/kwanmo2/waveshare-epaper-display
[6]:	https://code.mendhak.com/raspberrypi-epaper-dashboard/