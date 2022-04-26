---
layout: post
toc: false
comments: true
title:  Docker 컨테이너 + 한글 폰트 
description:  컨테이너 안에서도 한글을 써보자 
categories: [docker, data-science]

---

## 다른 방법 

이 [포스팅](https://anarinsk.github.io/lostineconomics-v2-1/docker/data-science/2020/09/24/install-hangul-in-docker.html)은 도커 컨테이너 안에서 한글 문제를 해결하는 다른 방법을 제시하고 있다. 같이 참고 하시라. 

## 왜 필요한가?

Jupyter 등에서 matplotlib을 쓸 때 라벨이 한글일 경우, 대부분 한글 출력에 문제를 겪게 된다. ㅁㅁㅁ형태로 출력되는데, 파이썬 환경에서 한글 폰트가 인식되지 않게 때문이다. 일반적인 환경이라면 웹 검색으로 찾을 수 있는 [가이드](https://financedata.github.io/posts/matplotlib-hangul-for-windows-anaconda.html)를 통해 해결할 수 있다.  

그런데 도커 환경을 쓴다면 이런 가이드가 별 소용이 없다. 도커는 아래 그림과 같이 'host os - 도커 - 컨테이너'의 구조로 돌아간다. 컨테이너(App x)가 각기 독자적인 os를 지니고 있기 때문에 해당 os에서 한글을 인식시켜줘야 특정 컨테이너 환경 안에서 한글을 쓸 수 있게 된다.  

![](https://www.docker.com/sites/default/files/d8/styles/large/public/2018-11/container-what-is-container.png?itok=vle7kjDj)

## Simple Solution 

방법은 간단하다. 컨테이너 환경 os에 직접 한글을 설치해주면 된다. 해당 os 내의 bash 혹은 상응하는 CLI에 들어가서 필요한 명령(스크립트)들을 실행하면 된다. 해당 명령들을 별도의 bash 스크립트로 만들고 필요한 경우 녀석들을 한방에 돌리면 살짝 더 편리할 것이다. 아래는 나눔 계열 폰트를 설치하는 스크립트다. 파일 이름을  `install_nanum.sh`로 하자. 

```shell
#!/bin/sh

sudo sed -i 's/archive.ubuntu.com/ftp.daumkakao.com/g' /etc/apt/sources.list
sudo apt-get update 
sudo apt-get install -y fonts-nanum*
sudo fc-cache -fv
```

나머지는 대체로 자명한 명령어다. 첫행의 sed는 ftp 주소를 국내로 바꿔주는 것이다. 업데이트 시 걸리는 시간을 단축하기 위해 사용했다. 터미널에서 스크립트 파일이 있는 디렉토리로 이동한 후 bash 스크립트를 실행하면 된다. bash 스크립트는 도커를 쓸 때 유용하다. 초기에 갖춰져야 하는 세팅이 있을 경우 스크립트로 만들어두고 도커 이미지를 새로 올렸을 때 실행해주면 되겠다. 약간 귀찮지만 못 견딜 정도는 아니다. 

```shell
> ./install_nanum.sh ⏎
```
윈도에서 파일을 편집할 경우 `^M`이 달라 붙어 문제가 생기는 경우가 있다. OS의 개행 문자가 달라서 생기는 문제다. docker 내부 터미널에서 `vim`, `nano` 등으로 파일을 열어 해당 부분을 지우고 다시 저장하면 된다. 

이제 도커 컨테이너 안의 이용한 주피터 노트북에서 다음과 같이 실행하면 나눔고딕 폰트를 쓸 수 있게 된다. 

```python
!./install_nanum.sh
import matplotlib.pyplot as plt
import matplotlib as mpl
from matplotlib import rc, font_manager
font_fname = '/usr/share/fonts/truetype/nanum/NanumGothic.ttf'
prop = font_manager.FontProperties(fname=font_fname)
mpl.rcParams['font.family'] = 'NanumGothic'
mpl.rcParams['axes.unicode_minus']  = False
font_manager._rebuild()
```
첫줄은 Jupyter 안에서 스크립트를 실행하는 명령어다.
혹시 잘 보이지 않으면, 커널을 한번 리프레시 해주면 된다. 다른 폰트를 설정하고 싶다면 비슷하게 응용해 활용하면 되겠다. 

### Updated 

2021년 5월 8일 기준으로 `font_manager`에서 `_rebuild()` 모듈이 없어졌더라. 현재 시점으로는 보이지 않았다. `install_nanum.sh`에서 `sudo rm -fr ~/.cache/matplotlib`를 추가로 하나 더 실행해주자. 캐시에 저장된 matplotlib의 폰트 리스트를 지워버리면 최초 실행될 때 자동으로 폰트 리스트를 빌드한다. 이때 설치한 일련의 나눔 폰트가 폰트 리스트에 잡힌다.  

Docker 컨테이너 내에 설치된 폰트를 확인하고 싶다면, 아래를 참고하라. 

```python
font_list = font_manager.findSystemFonts(fontpaths=None, fontext='ttf')
font_list
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5MjY3NTA1NCwxNzYzMTc5OTE3LC0xMj
E1OTc3NTk3LDEyMjgwMTk5NTMsMTQ1ODUxODUwLC0xODcwNjc5
OTQyLDE4MjI3Mzc0MzYsMTI5MjUwMTE2NCwtNDg5NDI0MzY2XX
0=
-->