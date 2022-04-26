---
layout: post
toc: false
comments: true
title:  Docker + Jupyter + 한글 폰트  
description: 빌드할 때 Jupyter의 한글 문제도 같이 해결하자!
categories: [coding, docker, jupyter]

---

## Build도 어렵지 않다! 

이 글은 [이 포스팅](https://anarinsk.github.io/lostineconomics-v2-1/docker/data-science/2020/09/24/install-hangul-in-docker.html)에서 이어진다. 컨테이너를 올린 뒤 컨테이너 내 터미널에서 sh 스크립트를 실행하지 않고 한글 문제 처음부터 해결할 수 없을까? 

사실 이 포스팅을 쓰게 된 동기는 따로 있다. 글을 쓰는 시점에서 `matplotlib.font_manager._rebuild()`가 사라졌다! Jupyter에서 폰트 목록을 다시 생성할 다른 방법을 찾아야 했다. docker-compose로 필요한 이미지를 끌어올 때 단순히 이미지를 끌어오는 대신 특화된 형태로 build를 할 수도 있다. 이전 포스팅에서 소개한 방법에서는 build 옵션을 사용하지 않았다. 일단 Build가 꽤 거창하게 느껴졌기 때문이다. 적당한 ubuntu 버전을 끌어오고 여기에 Python, Jupyter를 깔고... 이런 빌드 과정이 꽤 험난하고 불필요해 보였다. Jupyter의 경우 데이터사이언스를 위한 잘 갖춰진 도커 이미지가 이미 있고, 이를 그대로 쓰면 큰 문제는 없다. 

이제 문제가 생겼으니 해결책을 찾아야 한다. 이 특화된 이미지에 기반해서 빌드를 하면 한글 문제와 같은 특정하게 발생하는 문제를 미리 해결할 수 있지 않을까? 이후 소개하는 방법을 통해 확인한 내용은 다음과 같다. 이용 조건이 비슷하다면 참고해보시라.  

- docker-compose를 쓸 때 이미지를 지정하는 image 부분을 제외한 나머지는 거의 그대로 재사용이 가능하다. 
- image를 그대로 끌어오는 것이나 몇 가지 명령어를 넣어서 build를 하는 것이나 시간 상으로는 크게 차이가 없다. 

## How to Implement 

본론이다. 

1. docker-compose를 위한 file이 있는 디렉토리 아래 dockerfiles 디렉토리를 하나 더 만든다 (디렉토리 이름은 각자 알아서). 여기에 docker build를 위한 파일을 넣어어둔다. 
2. docker-compose용 파일을 약간 수정한다. 

### 실행 환경 

1. Windows 10 WSL 2 + Ubuntu 20.04 
2. Docker for Desktop (Windows)

### dockerfiles 

데이터 사이언스를 위한 Jupyter docker 파일을 예시로 들겠다. 다른 이미지라면 응용해서 쓰면 된다. 

```shell
FROM jupyter/datascience-notebook:latest
# Declare root as user 
USER root
# Update Ubuntu 
RUN sed -i 's/archive.ubuntu.com/mirror.kakao.com/g' /etc/apt/sources.list && sed -i 's/security.ubuntu.com/mirror.kakao.com/g' /etc/apt/sources.list
# Install Nanum for Korean Font 
RUN apt-get update && apt-get -y upgrade && apt-get install -y fonts-nanum* && fc-cache -fv && rm -fr ~/.cache/matplotlib
```

+ `FROM jupyter/datascience-notebook:latest` 끌어올 이미지를 지정한다. 
+ `USER root` 이미지 내에서 root 권한을 부여한다. 이후 sudo는 안 써도 된다. 
+ `RUN sed -i...` 끌어온 우분투 이미지가 미국 기준이기 때문에 업데이트 서버 주소 역시 미국이다. 이걸 국내에서 가장 안정적이고 빠른 카카오 서버로 바꾼다. 
+ `RUN apt-get update && apt-get -y upgrade...` 
    + 우분투 배포판의 업데이트 및 업그레이드를 실행한다.  
    + 나눔 폰트를 깔아준다. 
    + docker 이미지 배포판의 폰트 캐시를 지운다. 
    + Jupyter의 폰트 캐시를 지운다. 

### docker-compose.yml 

docker-compose를 위한 yml을 예시한다. 이 내용 역시 각자 환경에 맞게 변형해서 쓰면 된다. 파일 이름을 "docker-jupyter.yml"이라고 하자. 

```shell
version: '3'
#
services:
#
    jupyter-ds:
      build:
        context: .
        dockerfile: ./dockerfiles/dockerfile-jupyter
      user: root
      environment:
        - GRANT_SUDO=yes
        - JUPYTER_ENABLE_LAB=yes
        - JUPYTER_TOKEN={YOUR-PASSWORD}
      volumes:
        - /mnt/c/Users/{YOUR-DIR}:/home/jovyan/github-anari
      ports:
        - "8888:8888"
      container_name: "jupyter-ds"
# End of yml
```

+ 위의 yml 파일에서 "{}"로 처리된 부분은 각자 채워 넣으면 된다. 
+ image 대신 build 명령어를 사용했다. 앞서 지정한 dockerfiles 디렉토리 내의 도커 명령어를 통해 빌드를 수행한다. 이렇게 빌드된 이미지는 처음부터 matplotlib 사용 시 한글 구현에 아무런 문제가 없다. 

```shell
> sudo docker-compose -f /mnt/{YOUR DIR}/docker-jupyter.yml -p "jupyter-ds" up -d
```

실행 옵션은 다음과 같다. 역시 "{}"는 각자의 환경에 맞게 바꾸면 된다. 

+ `-f` 도커 콤포즈를 특정 파일로 실행하기 위한 옵션이다. 만일 이를 안쓰려면 yml 파일의 이름을 `docker-compose.yml`로 두고 해당 디렉토리 안에서 실행하면 된다. 
+ `-p` 콤포즈 안에 묶인 서비스의 이름을 나타낸다. 같은 네트워크로 묶이며 이 이름을 네트워크 이름으로 갖는다. 
+ `up` yml 내에 있는 포함된 콘테이너를 가동한다. 
+ `-d` 디태치 모드, 즉 별도의 실행되는 과정으로 실행한다. 

