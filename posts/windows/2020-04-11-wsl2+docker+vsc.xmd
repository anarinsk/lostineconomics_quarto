---
layout: post
toc: false
comments: true
title:  wsl 2 + docker + vsc 
description:  커널은 리눅스에 맡기시고, 코딩은 윈도에서 편안하게
categories: [wsl, visual-studio-code, docker]

---


## Assumptions 

### Abbreviation 

- tensorflow = tf 
- visual studio code = vsc 
- windows subsystem for linux version 2 = wsl 2 

### Rules 
- `|foo|`은 각자 환경에 맞게 설정해야 한다. 안에 쓴 단어는 되도록 해당 속성을 반영하고자 노력했다. 


## Mission 

- 한마디로 이중 원격 접속이다. 즉 wsl 2 안에 설치한 리눅스(1단계 원격 접속) 안에서 돌아가는 도커 컨테이너(2단계 원격 접속)에 vsc로 접근하기. 


## First Things First 

- wsl 2를 세팅하자. 
- docker desktop edge 버전 2.0 이상을 깔자. [여기](https://docs.docker.com/docker-for-windows/wsl-tech-preview/)를 참고하자. 
- [vsc](https://code.visualstudio.com/) 혹은 [vsc insider](https://code.visualstudio.com/insiders/)를 깔자. 

앞 두 개는 [여기](https://anarinsk.github.io/lostineconomics-v2-1/wsl/2020/04/09/wsl2-walkthru.html)를 참고하자.

## Pulling docker mage
- 이제 wsl 2를 통해 Ubuntu로 진입한다. 
- 도커가 제대로 설치되어 있다면 이미지들을 Ubuntu로 끌어올 수 있을 것이다. 시험 삼아서 tensorflow의 이미지를 끌어와보자. 

```shell
~$ docker run -it --rm tensorflow/tensorflow:latest-py3
```
- 이제 `wsl 2` -`Ubuntu` -`docker` 체제 아래 tf 컨테이너를 돌리는 데 성공했다! 사실 tf 설정이 조금 까다로울 수 있기 때문에(처음에 비해서는 많이 편리해졌다!) 이렇게 쓰는 편이 편할 수도 있다. 세 용은ttps://www.tensorflow.org/install/docker)를 참고하자. 

## Extensions for vsc 

- 우리의 목적은 wsl 2 아래 설치된 Linux 안에서 도는 docker container에 vsc로 접근해 편안한 환경에서 코딩하는 것이다. 그런데 생각해보면 곤란한 점이 있다. 
- vsc는 윈도에서 돌고 있다. 따라서 wsl 2를 거쳐 그 안에 깔린 ubuntu에 접근하는 것은 '원격' 접속의 개념이다. 그래서 해당 vsc 익스텐션 이름도 "Remote WSL"이다. 그런데 그 ubuntu 안에 설치된 도커 안에 있는 컨테이너에 접속하려면 원격-원격 접속, 즉 이중 원격 접속이 되는 셈이다. 이게 돼? 
- 원래는 
![]({{ site.baseurl }}/images/wsldockervsc/fig_1.png){: style="textalign:center; " width="800"}

-  Extensions에서 remote를 검색하면 `Remote Development`를 찾을 수 있다. 이 녀석은 `Remote WSL`, `Remote SSH`, `Remote Container` 세 개가 깔린다. 셋 다 유용한 extension이니 설치하도록 하자. 
- docker extension은 깔아도 좋고 안 깔아도 좋지만 docker를 쓸 거라면 깔아두도록 하자. 
- Extensions 중에서 remote explorer로 간 후 "container"를 선택하면 현재 돌아가고 있는 docker container를 확인할 수 있다.

![]({{ site.baseurl }}/images/wsldockervsc/fig_2.png){: style="textalign:center; " width="400"}
 
- 이 컨테이너를 vsc에 붙이면(attach) 끝이다! 허무하게 간단하다. 

![]({{ site.baseurl }}/images/wsldockervsc/fig_3.png){: style="textalign:center; " width="400"}
 
- 부착과 함께 별도의 창이 뜨면서 아래 그림처럼 윈도 앱 창 하단에서  컨테이너로의 이중 원격 접속이 잘 이루어졌음을 확인할 수 있다. 
	- 사실 이중 원격 접속이 아니다. docker가 wsl을 지원하기 때문에 vsc는 docker를 통해 바로 wsl 내에 돌고 있는 컨테이너에 접속하는 것이다. 

![]({{ site.baseurl }}/images/wsldockervsc/fig_4.png){: style="textalign:center; " width="400"}

- 컨테이너 익스텐션은 도커에 접속하기 위한 용도보다 훨씬 더 풍부하고 다양한 기능을 지니고 있다. 여기서는 도커 접속을 위한 도구로만 접근하도록 하자. 자세한 것은 [여기](https://code.visualstudio.com/docs/remote/containers)를 참고하자. 

### Trouble shooting 

- 가끔 접속 단계에서 에러가 발생하는 경우가 있다. `Remote - Container` 익스텐션이 docker에 접속하지 못하면서 생기는 일로 추정된다. 내 경우는 아래의 작업으로 문제를 해결했다.[^3] 

----

1. `Win + R` 실행  
2. `%appdata%` 입력 후 엔터 
3. `Code`, `Code - insider` 폴더를 찾아서 지운다.
4. vsc, vsc insider를 다시 실행한다. 

----

- 여튼 "disconnected from..." 메시지와 함께 컨테이너에 접속이 안되거나 접속에 문제가 생길 때 이 방법을 쓰시라.

[^3]: 출처는 [여기](https://stackoverflow.com/questions/47689536/uninstall-visual-studio-code-in-windows). 경우에 따라서는 소프트웨어 전체를 언인스톨해야 하는 경우가 있을지도 모르겠다. 

## For what? 

- docker의 용도가 그렇지만 필요한 컨테이너를 끌어다가 마음껏 활용하고 문제가 생기면 버리면 된다. 도커를 쓴다면 사실 python 가상 환경조차 필요 없다. 필요한 패키지가 깔린 파이썬 환경을 만들어두고 도커로 끌어와 쓰면 그만이다. 
- vsc가 윈도에서 돌기 때문에 작업중인 파일 등은 docker container 내에 두지 않아도 된다. 유연하다!
- 재현 가능성은 연구에서만 문제가 되는 것이 아니다. 소프트웨어 개발에서 상호 의존성 때문에 구현된 환경을 관리하는 것이 못지 않게 중요하다. 도커는 이런 점에서 거의 완벽한 솔루션이다.[^1]

[^1]: 사족을 달자면 데이터 사이언스 그리고 컴퓨터 작업이 중요해지는 분야라면 학술이든 산업이든 실용이든 도커의 활용이 필수적이라고 생각한다. 그렇게 갈 것이다, 마...  

## Making Pandas Docker 

- 이제까지 살펴본 내용을 바탕으로 아래의 요소를 지닌 도커를 만들어 보자. 
	- ubuntu 18.04 
	- python 3.7 
	- pandas 1.0.3
- 먼저 이 될만한 컨테이너를 끌어와야 한다. 바탕이 될 만한 필요한 컨테이너는 왠만하면 Docker Hub에서 찾을 수 있다. 그리고 자신의 이미지를 관리하고 활용하고 싶다면, Docker Hub에도 가입해두도록 하자.[^2] 
- 도커 컨테이너를 제대로 빌드하려면 이것 보다는 살짝 복잡하다. 하지만 나는 언제나 야매지만 빠른 방법이 좋더라. 
- 윈도에서 wsl 기반의 도커를 쓰는 또 하나의 장점이 있다. 윈도 도커 앱이 wsl 내에서 돌고 있는 도커 컨테이너를 별도로 관리한다. 따라서 터미널로 wsl을 호출하고 있지 않은 상태에서도 wsl 내의 도커는 실행상태다. 따라서 터미널 앱 없이도 vsc에서 컨테이너에 접속해 작업이 가능하다. 
- 원 
![]({{ site.baseurl }}/images/wsldockervsc/fig_8.png){: style="textalign:center; " width="700"}

[^2]: ubuntu 보다 가벼운 alpine 같은 리눅스 버전을 써보면 어떨까? [여기](https://pythonspeed.com/articles/alpine-docker-python/)에 따르면 별로 좋지는 않다고 한다. 용량이나 성능의 큰 이슈가 없다면 그냥 ubuntu를 쓰는 편이 좋을 듯 하다. 

### Pull ubuntu 18.04 

[여기](https://hub.docker.com/_/ubuntu?tab=tags)를 참고해서 필요한 컨테이너 이미지를 끌어오자. 내 경우는 18.04를 가져왔다. 

```shell
~$ docker pull ubuntu:18.04
```

이렇게 끌어온 이미지를 컨테이너에 태워 실행시켜보도록 하자. 

```shell
~$ docker run -it |image-id-of-container|
```

이제 ubuntu 18.04 위에 ubuntu 18.04가 올라갔다! 재미있는 일이 아닌가! 

- Ubuntu를 깔았을 때 필요한 기본적인 작업을 하고, 파이썬을 깔고 필요한 패키지를 깐다. 기본적으로 local ubuntu에서 했던 일을 동일하게 해주면 된다. 단 `sudo`는 붙일 필요가 없다. ubuntu 이미지 자체가 root로 태워져 있으므로 모든 명령어는 기본적으로 sudo가 붙어 있다고 보면 되겠다. 

### How to ommit / ag / ush Image 

- 이렇게 별도의 작업을 거친 컨테이너는 애초에 끌고 왔던 이미지와는 달라졌을 것이다. 그런데 도커의 속성상 콘테이너를 내리게 되면 변경했던 내용들은 다 사라진다. 이렇게 변경된 콘테이너를 저장할 수 있어야 한다. 

```shell
~$ docker ps 
```

![]({{ site.baseurl }}/images/wsldockervsc/fig_5.png){: style="textalign:center; " width="700"}

```shell
~$ docker commit |container-name or id-of-container| |name-of-image|
```

- 이제 저장된 이미지를 확인해보자. 

```shell
~$ docker images 
```

- 이렇게 확인된 이미지 중에서 docker hub로 보내고 싶은 이미지에 태그를 걸어준다. 

```shell
~$ docker tag |image-id| |id-of-docker-hub/name-of-docker-hub-image| 
```

- 다시 이미지를 조회해보면 `|id-of-docker-hub/name-of-docker-hub-image|` 이미지가 생성되었을 것이다. 이제 이 이미지를 도커 허브로 푸시하면 된다. 

```shell
~$ docker push |id-of-docker-hub/name-of-docker-hub-image|
```

- 이미지의 상태가 지저분하다고 느끼면 다 지우고 다시 pull 하면 된다. 이미지를 모두 삭제하려면, 아래와 같이 실행하자. 

```shell
~$ docker rmi -f $(docker images -a -q)

```

- 기본적인 Ubuntu update와 python3.7 그리고 pandas, matplotlib가 설치된 이미지를 당겨와 실행해보자. 

```shell
~$ docker run -it --rm anarinsk/py37-pandas 
```

- 위에서 설명한대로 vsc를 통해 작업하면 된다. 안에  testcode.py라는 간략한 실험 코드를 넣어 두었다. 

![]({{ site.baseurl }}/images/wsldockervsc/fig_6.png){: style="textalign:center; " width="700"}

### Dockerfile 

- 사실 빌드를 이렇게 수작업으로는 할 수 없는 일이 아닌가? 도커 자체에서 만든 빌드를 위한 마크업 랭귀지가 따로 있고 이 녀석을 `Dockerfile` 이라는 형태를 통해서 구현할 수 있다. 
- 도커 컨테이너를 생성하는 데 필요한 단계를 넣어두고 빌드에 성공하면 해당 이미지가 생성되는 편리한 방식을 따르고 있다. 
- 도커 허브에서는 github와 연결하여 github에 새로운 내용이 커밋되었을 자동으로 도커 허브의 빌드를 구현해주는 자동화 빌드까지 구현되어 있다. 
- 도커 빌드에 관해서 보다 상세한 사항은 [여기](https://www.44bits.io/ko/post/how-docker-image-work)를 참고하자. 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2NDg0NTEzLDIwMTQ1NzMyMjIsNDA4Mj
QyNzE1LC0xMTg3ODc0NDAyLDg4NjI5NTgyNSwtMTQ4MjA2Mzcw
NiwtNTE1ODcwOTY2LC00MjQyNjkwMCwxMDA4MDM3MDE4LDc1NT
c2ODQ1NiwxOTY2MTc5MDA0LC00OTE1NTY2MzAsMTU4MjM2NjU4
MiwxNzIxMzMxNjc5LDY1OTU4MTA3NSwtMTYyOTQ1NDAyMCwtOD
M2OTcwNzE1LDU1NTc4OTI3OSwxODEwNzYzMzkxLDE2NjkxNDMy
MDJdfQ==
-->