---
title:  "Libcamera 설치"
search: true
categories: 
  - Embeded Vision
  - Software
tags:
  - Python
---

라즈베리파이에 libcamera가 기본으로 설치되어있어야할 것 같은데 미설치로 인한 오류 발생.
나는 32비트 라즈비안 OS에서만 시도해봄.
직접 설치하기 위해서 아래 사이트 확인.

[Getting Started - libcamera](https://libcamera.org/getting-started.html)

생각보다 설치 방법이 복잡하다. 자신의 환경에서 다시 컴파일 빌드를 해줘야함.

가장 먼저 필요한 것은 CMake 설치

```bash
sudo wget https://cmake.org/files/v3.24/cmake-3.24.2.tar.gz
sudo tar -xvzf cmake-3.24.2.tar.gz

sudo ./bootstrap --prefix=/usr/local && sudo make && sudo make install

```
Ninja 설치 후, meson 설치. 

```bash
sudo apt install build-essential
sudo apt install ninja-build

python3 -m pip install meson

meson --version
ninja --version
```

Meson으로 C++ 빌드를 테스트해보고 싶다면 아래 사이트 확인

[CMake는 가라! Meson과 함께하는 차세대 C++ 빌드 시스템 구축 - 인하대학교 인트아이](https://int-i.github.io/cpp/2021-06-26/cpp-meson/)

meson build를 해보았지만 몇가지 필수 패키지가 빠져있다고 에러가 발생.
나머지 필수 패키지를 설치해보자
```bash
sudo apt-get install -y libyaml-dev
sudo apt install python3-yaml
sudo apt install python3-ply
```

optional 부분은 선택적으로. 일단 혹시몰라 아래의 패키지는 모두 설치함.
참고로 스트리밍(실시간)으로 이미지를 전송하기 위해서는 gstreamer는 많이 쓰기 때문에 설치할 것을 추천

**for improved debugging: [optional]**
libdw-dev libunwind-dev

**for device hotplug enumeration: [optional]**
libudev-dev

**for documentation: [optional]**
python3-sphinx doxygen graphviz texlive-latex-extra

**for gstreamer: [optional]**
libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev

**for cam: [optional]**
libevent-dev is required to support cam, however the following optional dependencies bring more functionality to the cam test tool:
• libdrm-dev: Enables the KMS sink
• libjpeg-dev: Enables MJPEG on the SDL sink
• libsdl2-dev: Enables the SDL sink

**for qcam: [optional]**
qtbase5-dev libqt5core5a libqt5gui5 libqt5widgets5 qttools5-dev-tools libtiff-de