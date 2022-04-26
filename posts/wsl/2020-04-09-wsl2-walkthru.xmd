---
layout: post
toc: false
comments: true
title:  wsl 2, a walk-thru
description:  wsl 2의 열기를 느껴보아요~ 
categories: [wsl]

---

격세지감이다. 적으로 삼고 아웅다웅하던 윈도가 리눅스를 두 팔로 품었다. (마치 macos에서 처럼) 윈도에서 터미널을 켜고 리눅스를 네이티브로 쓸 수 있을 것이라고 누가 생각했을까. 그런데 그런 날이 왔네. MS, 대단하다.  

WSL(Windows Subsystem for Linux)의 두 번째 버전(이하 wsl 2)은 좋다. 그냥 좋다. wsl 2을 통해 모든 리눅스의 장점을 네이티브로 누릴 수 있다. wsl 2는 이 글을 작성하는 현재 시점까지 별도로 신청해야 하는 윈도 프리뷰를 통해서 사용할 수 있다. 상반기에 예정된 [2004 업데이트](https://www.neowin.net/news/windows-10-version-2004-is-coming---heres-what-you-need-to-know-about-it/)에 정식으로 포함될 예정이다.

이 포스트는 그간 짬짬이 써오면서 알아왔던 내용을 한방에 정리하기 위한 용도다. 역시나 친절한 가이드, 이런 것과는 거리가 멀고 몇 달 후의 '나놈'을 위한 것임을 밝혀둔다.[^4]

[^4]: 상세한 다른 가이드로는 [여기](https://pbpython.com/wsl-python.html)를 참고하자. 

## Ubuntu 18.04 설치 

- [여기](https://docs.microsoft.com/ko-kr/windows/wsl/install-win10)를 참고하면 되겠다. 
- 다른 리눅스를 써도 좋다. 일단 가장 대중적인 Ubuntu로 가보자. 

## Windows Terminal 

- [이전](https://anarinsk.github.io/lostineconomics-v2-1/coding-tool/python/wsl/2020/03/19/WSL_Cmder.html)에 CLI 도구로 Cmder를 추천한 바 있다. 그런데, 1004 버전부터 MS가 공식 터미널 앱을 넣어 놓았다. Windows Terminal 하나면 PowerShell, Windows cmd, Unbuntu를 탭으로 자유롭게 오갈 수 있다. 속도도 빠르고 커스터마이징도 어렵지 않게 가능하다. 안 쓸 이유가 없다. 
- 한가지 단점. 복붙이 자유롭지 않다고 바로 느낄텐데, 터미널 안에서는 CRTL-C/V 대신 CRTL+SHIFT-C/V로 다시 키매핑이 되었다. 터미널 외부에서는 기존 방식이고 안에서는 SHIFT가 더해진 방식이다. 살짝 의아하지만 못 쓸 정도는 아니니까 참고 넘어가자. 
-  커스터마이즈는 VS Code를 활용해서 쉽게 구현할 수 있다.  [여기](https://dev.to/expertsinside/how-to-customize-the-new-windows-terminal-with-visual-studio-code-56b1)를 참고하자. 

### Some command 

```shell
wsl -l -v # in Powershell or cmd 
wsl.exe -l -v # in Ubuntu terminal 
```

![]({{ site.baseurl }}/images/wsl2-wt/fig_1.png){: style="textalign:center; " width="600"}

![]({{ site.baseurl }}/images/wsl2-wt/fig_2.png){: style="textalign:center; " width="600"}

- 만일 PowerShell(PS)이나 cmd 안에서 친다면 위와 같이, 그리고 Ubuntu 터미널 안에서 친다면 아래와 같이 치면 된다. 자신이 쓰고 있는 가상 OS의 이름과 버전을 확인할 수 있다. 보시는것처럼 wsl version 2로 잘 나타나야 한다.  
- 하나 알 수 있는 사실. Ubuntu 터미널 안에서 윈도우 앱도 실행할 수 있다.

아래 두 명령어를 통해서는 버전을 설정하거나 혹은 사용중인 배포판을 디폴트로 설정할 수 있겠다. 

```shell
wsl --set-version (distro name) 2
wsl --set-default <distro name>
```

예컨대, Ubuntu-18.04를 기본 배포판으로 설정하고 싶다면 아래와 같이 PS에서 실행하면 된다. 

```shell
wsl --set-default Ubuntu-18.04 
```


## Docker Desktop 

- 만일 Ubuntu를 유일한 OS로 쓰고 있다면 docker, kubernetes(k8s)를 별도로 설치해야 한다. wsl 2에서는 그럴 필요가 없다. 
- [docker desktop for windows](https://docs.docker.com/docker-for-windows/edge-release-notes/)의 엣지버전  v 2.2.3.0(43965) 이상을 깔면 윈도 상에서 리눅스 터미널을 쓸 때 docker와 k8s이 자연스럽게 설정된다. 그냥 터미널을 열고 쓰면 된다! 

![]({{ site.baseurl }}/images/wsl2-wt/fig_3.png){: style="textalign:center; " width="700"}

![]({{ site.baseurl }}/images/wsl2-wt/fig_4.png){: style="textalign:center; " width="700"}

- 여러 버전의 리눅스가 깔려 있을 경우 윈도의 도커 앱에서 위 첫번째 화면에서처럼 선택해서 사용할  수 있다.  
- 보다 상세한 내용은 [여기](https://docs.docker.com/docker-for-windows/wsl-tech-preview/)를 참고하자. 


###  Hello-world for docker 

- docker가 잘 돌고 있는지 확인하고 싶다면 헬로우월드를 돌려보면 되겠다. 

```shell
~$ sudo docker run hello-world
```

- 내가 docker를 Ubuntu에 깐 적이 없어도 아래 같이 잘 출력될 것이다. 리눅스 배포판에 맞춰서 연동되는 개념이라고 여기면 되겠다. 

![]({{ site.baseurl }}/images/wsl2-wt/fig_5.png){: style="textalign:center; " width="600"}

## Testing Kubernetes 

- 쿠버네티스도 잘 도는지 확인해보자. [여기](https://blog.aliencube.org/ko/2018/06/04/running-kubernetes-on-wsl/)에서 가져왔다. 

```shell
~$ kubectl cluster-info
```

최초로 포드를 세팅하는 것이라면 아래의 코드를 실행해주자. 

```shell
~$ kubectl run hello-minikube --image k8s.gcr.io/echoserver:1.10 --port 8080
~$ kubectl expose deployment hello-minikube --type NodePort
```

돌고 있는 서비스의 정보를 확인하자. 

```shell
~$ kubectl describe service hello-minikube
```

여기서 `NodePort`를 확인해서 웹 브라우저에서 `localhost:XXXXX`라고 쳐주면 아래와 같이 떠야 한다. 

![](https://sa0blogs.blob.core.windows.net/aliencube/2018/06/running-kubernetes-on-wsl-09.png){: style="textalign:center; " width="600"}



## Best Practices for python

- wsl 2에 파이썬을 넣고 쓴다면 아래와 같은 두 가지 원칙을 유지하면 좋다. 
	1. conda 같은 배포판 말고 그냥 파이썬을 쓰자. 
	2. 디폴트 가상 환경 venv를 활용하자. 

- 이 두가지 원칙을 예시한 아래의 포스팅을 참고하시라.  
	1. [네이티브 파이썬 설치](https://anarinsk.github.io/lostineconomics-v2-1/coding-tool/python/2020/03/17/vanilla-python.html)
	2. [python venv 활용](https://anarinsk.github.io/lostineconomics-v2-1/coding-tool/python/venv/2020/04/04/python-venv.html)

- 도커로 특정 파이썬 환경을 끌어와 쓰는 것도 가능하다. 예를 들어 tensorflow 설정이 복잡하다면 그냥 docker로 끌어다쓰면 된다. 

## git, also natively 

- git도 모양 빠지게 윈도우 용을 별도로 깔 필요가 없다! 만세! wsl 2 ubuntu에 탑재된 녀석을 쓰면 된다. 
- 윈도 폴더에는 어떻게 접근하면 될까? 친절하게도 `/mnt/c`, `/mnt/d`와 같은 식으로 이미 Ubuntu root 디렉토리에 마운트가 되어 있다. wsl 내에서도 원도용 폴더로도 쉽게 접근할 수 있다. 

###  github login 

- 하나 문제가 될 만한 것은 github의 로그인이다. 매번 아이디/패스워드를 쳐 넣기 귀찮을 수 있다. 
- 좋은 해결책은 rsa 공개키를 생성해서 ssh로 로그인 터널을 만들어두는 것이다. git별로 클론할 때 한번만 해두면 되니 꽤 편리하다. 자세한 것은 [여기](https://proni.tistory.com/entry/%F0%9F%90%A7-Ubuntu-Git-username-password-%EC%97%86%EC%9D%B4-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)를 참고하자. 
- 단 사내 네트워크 같은 곳에 물려 있을 경우 ssh 접근이 원활하지 않을 수 있다. 




<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyODc0NjQ5MCwtMzQ3MzAxMTIzLC0xOD
Q4MTYwNDk5LC0xOTE4MzY1ODExLC0xNjE1NjgwODU1LDQ4Mzg3
MTMwNiw4NjA1NzQxNjgsMTAxODEzMzU4OSwtNDk5MzE5NDUsLT
g3MDU4OTE1LDU2MTYzNjU2NywtMTIyODA3NDE1LDE1NzY4MDQ3
ODcsLTEwMTcxNjk1MjIsLTE4NzQ2NDk1NDAsNTg1NTkxOTMwLC
0yMDU3ODI5NzgyLDEzNTYzNTg1ODgsLTE2Njc2Nzk1MCwyMDcy
NzQ5MDE3XX0=
-->