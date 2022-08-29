---
title:  "Verilog HDL 연습 시작"
search: true
categories: 
  - Hardware
tags:
  - Verilog HDL
---
# 개요
Mac에서 Verilog HDL을 연습하기란 꽤나 귀찮은 일이다. Xilinx Vivado도 본격적으로 linux가 필요하고, 맥은 윈도우처럼 WSL도 안되기 때문이다. 제대로 된 시뮬레이션을 돌려보고, 실제 장치에 올리기 위해서는 결국 네이티브 리눅스 PC, 또는 윈도우 PC가 필요하다. 그럼에도 개인용 노트북은 맥을 사용하고 있기 때문에 어쩔 수 없이 맥에서 강의를 들으면서 Verilog HDL을 연습할 수 있는 방법은  icarus Verilog를 사용하는 방법 뿐이다.

# 설치 방법
모든 설치는 Mac에서 패키지 설치 시 자주 사용하는 brew를 통해서 진행하는게 좋다. Verilog HDL 시뮬레이션에 사용할 이카루스는 다음과 같이 간단하게 설치할 수 있다.

```terminal
brew install icarus-verilog
```

waveform을 볼 수 있는 가장 유명한 툴인 gtkwave는 mac에서도 사용할 수 있다. 
다만 설치하고 bashrc 설정을 해야하는 번거로움은 있다. 
https://ughe.github.io/2018/11/06/gtkwave-osx

```terminal
brew cask install gtkwave
brew install gtkwave --cask
```

# 실제 사용 방법

실제 사용은 다음과 같이 한다. 

- Verilog HDL 코드에 .vcd dump파일 생성을 명시한다
```verilog hdl
initial begin
	$dumpfile("sample_tb.vcd");
	$dumpvars(0,tb_counter_100);
```

- icarus Verilog를 이용하여 output 파일을 생성한다. 
```terminal
iverilog -o tb_counter_out counter.v tb_counter.v
```

- $display 출력은 다음과 같이 간단하게 확인할 수 있다.
```terminal
vvp tb_counter_out
```

- GTKwave같은 툴을 이용하여 파형을 확인하면 된다. 
```terminal
gtkwave ./sample_tb.vcd
```

<p align="center">
	<img width="460" height="300" data-action="zoom" src= "/assets/MyImages/Pasted image 20220829211727.png" >
</p>

이 정도 시뮬레이션만 되도 간단하게 Mac으로 Verilog HDL 연습은 가능해보인다. hardware도 이미 구매했으니 빨리 Verilog HDL 언어를 익혀서 유의미한 결과를 낼 수 있게 연습과 시간이 필요하다. 