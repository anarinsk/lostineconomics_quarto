---
layout: post
toc: false
comments: true
title:  WSL without Docker Desktop
description: Docker Desktop 없이 콘테이너를 써보자
categories: [coding]
---

# From Docker to Podman 

도커 데스크탑의 유료화 정책이 발표되었다. 대부분의 사용자나 회사에게는 해당 사항이 없겠지만, 오픈소스로 시작한 회사의 정책이라고 보기에는 뭔가 께름칙하다. 대안이 있는데도 굳이 고집할 필요는 없다. 여러 프로젝트가 복잡하게 의존하는, 즉 발목 잡힌 상황이 아니라면 다른 길을 찾으면 된다. 

WSL 내에서 컨테이너를 돌리고 이 서비스를 윈도우에서 웹브라우저로 끌어다 쓰는 형태가 내 일상적인 작업 환경이다. Docker Desktop이 중요한 역할을 하고 있지만 발목은 잡힐 것이 없기에 대안을 시도해보기로 했다. 사실 WSL 내에서 도커를 쓰면 약간 '가짜'인 듯한 기분이 들 때가 있다. Docker Desktop은 WSL을 거의 완벽에 가깝게 지원한다. 그런데 구조를 뜯어보면 조금 복잡하다. Docker Desktop이 docker 엔진 활용을 위한 두 개의 자체의 컨테이너를 만들고, 이 둘이 WSL과 통신한다. 즉 도커 컨테이너가 WSL 안의 OS에서 돌고 있지 않다는 뜻이다. Windows 및 WSL 지원을 구현하기 위한 궁여지책을 사용하는 느낌이다. 

docker 엔진 대신 나름 쓸만한 녀석이 podman이다.[^1] podman은 OCI(Open Container Initiative)의 표준을 준수하며 docker와 거의 모든 면에서 호환된다. docker의 명령어 뿐 아니라 docker에서 활용하는 이미지도 그대로 쓸 수 있다. 

[^1]: podman에 관한 기술적 설명은 [LINK](https://naleejang.tistory.com/m/227), [LINK](https://www.s-core.co.kr/insight/view/oci%EC%99%80-cri-%EC%A4%91%EC%8B%AC%EC%9C%BC%EB%A1%9C-%EC%9E%AC%ED%8E%B8%EB%90%98%EB%8A%94-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%EC%83%9D%ED%83%9C%EA%B3%84-%ED%9D%94%EB%93%A4%EB%A6%AC%EB%8A%94/)를 참고하자. 

비유를 하자면 컨테이너를 운반하는 배가 바뀔 뿐 컨테이너 자체는 그대로 운용할 수 있다. 아울러 podman을 쓰면 앞서 말한 Docker Desktop의 복잡한 구조가 필요 없다. podman은 WSL 에 설치된 OS 안에서 운용된다. 그리고 podman은 엔진을 제외한 docker 생태계의 다른 요소들과 함께 쓸 수도 있다. 내 경우 작업 환경을 유지하는데 docker-compose가 중요한 역할을 한다. 이 녀석도 podman과도 잘 어울렸다. 각설하고 내용으로 바로 들어가보자.[^2] 

[^2]: 윈도에서 Docker Desktop 버전을 사용하는 대신 Docker CE 버전을 WSL-Ubuntu에 깔아서 사용할 수 있다. 이 글을 관심은 docker를 대체하는 데 있으니, 이에 관한 내용은 다루지 않는다. 

# Problems 

내용을 살펴보기 전에 아래와 같은 내용을 가정한다. 

## Assumptions 

- WSL 2가 잘 깔려 있고 설정되어 있다. 
- Ubuntu 20.04가 깔여 있고 업데이트도 잘 되어 있다. 
- Docker Desktop이 깨끗하게 언인스톨되어 있다.

이 가정에 관해서는 별도로 설명하지 않겠다. 구글 검색을 하시면 관련한 좋은 포스팅이 많이 나올 것이다. WSL에 관해서는 [MS의 공식 가이드](https://docs.microsoft.com/ko-kr/windows/wsl/install-win10)도 더할 나위 없이 잘 되어 있다. 

podman에 관해 내가 풀고 싶은 문제는 세 가지다. 

1. docker를 podman으로 대체하기 
2. podman으로 nvidia gpu 부리기 
3. podman과 함께 docker-composer 쓰기 

1, 2의 방법은 Ubuntu 20.04에서 그대로 활용할 수 있다. 3의 경우 WSL이 지니는 OS 구조의 특성 때문에 몇 가지 추가적인 작업이 필요하다.  

# Enter the podman 

출처를 먼저 적어 두었으니 필요한 경우 바로 참고하면 되겠다. 

## References 

- [LINK](https://wbhegedus.me/running-podman-on-wsl2/)
    + 잘 되어 있지만 진행 순서에 살짝 오류가 있어서 아래 수정했다. 
- [LINK](https://podman.io/getting-started/installation#installing-development-versions-of-podman)


## Basics

최신 버전의 podman을 설치하기 위해서는 apt 저장소의 주소를 별도로 업데이트해줘야 한다. 20.10 이후부터는 podman을 공식적으로 지원하고 있다. 다음번 Ubuntu LTS 버전이 나오면 PPA를 추가하는 이슈는 해소될 듯 싶다. 

```shell
1$ cat /etc/lsb-release
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=20.04
DISTRIB_CODENAME=focal
DISTRIB_DESCRIPTION="Ubuntu 20.04.2 LTS"

2$ export VERSION_ID="20.04"

echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/ /" | sudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
curl -L https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key | sudo apt-key add -
sudo apt-get update
sudo apt-get -y upgrade
sudo apt-get -y install podman
```

- 셸 스크립트에서 `1$`, `2$`라고 되어 있는 부분은 설명이 필요한 부분이다. 실행을 할 때는 `$`이후만 필요하다.  

1. `1$`은 현재 설치된 Ubuntu의 버전 등을 알아내는 대목이다. 
2. 이를 통해 `VERSION_ID` 변수를 설정한다. 

- 나머지 부분은 PPA를 설정하고 패키지 저장소를 업데이트하고 포드맨을 설치하기 위한 작업이다. 

## Setting 

많은 가이드를 보면 아래 두 파일 중 하나의 내용을 수정할 것을 권고하고 있다. 후자의 파일은 없기 때문에 생성하면 된다. 

- `/usr/share/containers/containers.conf` 
- `~/.config/containers/containers.conf`

수정 혹은 생성 내용은 아래와 같다. 

```txt
[engine]
events_logger="file"
cgroup_manager="cgroupfs"
```

- 그런데 굳이 고치지 않아도 컨테이너를 돌리는 데 큰 이슈는 없는 듯 싶다.

## Testrun 

podman이 잘 깔렸는데 아래와 같이 테스트해보자. 

```shell
podman run hello-world 
```

docker의 hello-world를 테스트로 사용하면 된다. 잘 되었다면 잘 깔린 것이다. 

# Podman + nvidia GPU 

Docker Desktop을 쓰면서 제일 좋았던 대목이 nvidia GPU에 관한 지원이다. docker에서 `gpu` 옵션이 지원되서 nvidia docker를 별도로 깔 필요가 없다. 

왜 이게 편리할까? 컨테이너를 쓰면 각종 복잡한 설정을 우회해서 바로 필요한 상태를 올릴 수 있다. Ubuntu에서 GPU를 부리기 위한 준비가 간단하지 않다. 각종 드라이버 및 API를 설치하는 수고로움을 피하기 위해서 해당 준비가 갖춰진 컨테이너를 올려 쓰면 된다. Podman에서 이게 어렵다면 그 매력이 떨어지지 않을까? 

다행스럽게도 nvidia에서 컨테이너를 위한 런타임을 제공한다. 이 녀석을 설정해주면 podman과 nvidia GPU를 쉽게 연결할 수 있다. 

## References

- [LINK](https://nvidia.github.io/nvidia-docker/)
- [LINK](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#id8)

## Installation 

nvidia 컨테이너 툴킷 설치를 위해서 먼저 PPA를 설정하자. 

```shell
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update
```

컨테이너 툴킷을 설치한다. 

```shell
sudo apt install -y nvidia-container-toolkit
```

`/usr/share/containers/oci/hooks.d/oci-nvidia-hook.json` 파일이 있는지 확인해본다. 없으면 생성하고 아래의 내용을 담도록 하자. 

```json
{
    "version": "1.0.0",
    "hook": {
        "path": "/usr/bin/nvidia-container-toolkit",
        "args": ["nvidia-container-toolkit", "prestart"],
        "env": [
            "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
        ]
    },
    "when": {
        "always": true,
        "commands": [".*"]
    },
    "stages": ["prestart"]
}
```

`/etc/nvidia-container-runtime/config.toml` 파일을 수정하도록 하자. 아래 코드를 통해, config.toml에서 필요한 부분을 수정하고 제대로 수정되었는지 조회한다. `no-cgroups = true`를 설정하는 것이 핵심이다. 파일을 에디터로 열어 직접 수정해도 된다. 

```shell
$ sudo sed -i 's/^#no-cgroups = false/no-cgroups = true/;' /etc/nvidia-container-runtime/config.toml
$ cat /etc/nvidia-container-runtime/config.toml
```

부팅을 다시 해주자. WSL에서 나갔다가 다시 들어가면 된다. 셸 자체를 껐다가 다시 켜도 된다. 

## Testrun 

아래 예는 nvidia-smi 명령을 통해서 OS에 드라이버가 제대로 설정되어 있는지 확인하는 명령어이다. WSL이 깨끗하게 설치된 상태라면 WSL-Ubuntu에는 nvidia driver가 설치되어 있지 않다. 컨테이너를 통해서 드라이버가 설정된 이미지에 진입해 GPU를 부리는 것이라고 보면 되겠다. 단 하드웨어와 직접 소통하는 윈도 드라이버가 WSL2을 지원하는 버전인지 여부는 꼭 확인하시라. 최신 버전은 대체로 WSL2를 잘 자원한다.   

```shell
podman run --rm --security-opt=label=disable nvidia/cuda nvidia-smi
```

CUDA를 활용한 nbody example도 돌려보자. 

```shell
podman run --env NVIDIA_DISABLE_REQUIRE=1 nvcr.io/nvidia/k8s/cuda-sample:nbody nbody -gpu -benchmark
```

# Podman + Docker Compose 

Docker Desktop은 docker 생태계를 구성하는 컨테이너 관련 구성물을 윈도 및 여타 OS에 맞게 변형하고 집약한 제품이다. 이것이 유료화되는 것이지 CE 버전 및 리눅스 배포판에서 쓸 수 있는 도커 생태계를 구성하는 각종 요소가 모두 유료화되는 것은 아니다. 오픈소스 라이선스의 특성을 생각할 때, 이러한 개별 요소들이 모두 유료화되지는 못할 것이다.  

docker 생태계의 편리한 앱 중 하나가 docker-compose다. 이 녀석이 여러 개의 컨테이너를 각각의 조건을 걸어 한번에 올려 놓고 선택해서 쓰는 용도에 딱 맞다. 내 경우는 Jupyter, RStudio, Tensflow-Jupyter 세 개의 컨테이너를 올려 놓고 돌려가며 쓴다. 

## Reference 

[LINK](https://github.com/arkane-systems/genie)

## Problem 

WSL이 Ubuntu의 systemd를 처음부터 활성화하지 않는다. docker CE 버전을 데스크탑을 거치지 않고 WSL 안에서 깔아서 쓸 때 이게 문제가 된다. systemd를 먼저 활성화해야 한다. 

## Solution 

### Runtime 

- 먼저 MS 런타임을 설치하자. 

```shell
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```

### wsl-transdevian 

- 이 녀석을 설치하기 위해서 먼저 lsb를 설치하자. 

```shell
sudo apt-get install lsb 
```

- sudo로 실행되어야 하는 항목에서 이를 타이핑하는 번거로움을 피하기 위해서 `sudo -s`를 실행하자. 이후 아래 스크립트를 실행한다. 

```shell
wget -O /etc/apt/trusted.gpg.d/wsl-transdebian.gpg https://arkane-systems.github.io/wsl-transdebian/apt/wsl-transdebian.gpg
chmod a+r /etc/apt/trusted.gpg.d/wsl-transdebian.gpg

cat << EOF > /etc/apt/sources.list.d/wsl-transdebian.list
deb https://arkane-systems.github.io/wsl-transdebian/apt/ $(lsb_release -cs) main
deb-src https://arkane-systems.github.io/wsl-transdebian/apt/ $(lsb_release -cs) main
EOF

apt update
```

### genie & docker-compose 

이제 마지막으로 genie와 docker-compose를 설치해준다. 

```shell
$ sudo apt update
$ sudo apt install -y systemd-genie
$ sudo apt install docker-compose
```

### Setting 

```shell
1$ systemctl --user start podman.socket
2$ export DOCKER_HOST=unix://$XDG_RUNTIME_DIR/podman/podman.sock
```

1. `systemctl...` 명령을 통해서 podman의 소켓을 시작한다. 소켓의 상태를 보고 싶다면 `start` &rarr; `status`로 바뀌 실행해보자. 
2. docker가 설치되지 않았기 때문에 docker-compose가 쓸 수 있는 가상화 앱을 지정해야 한다. 이를 위에 열어준 포드맨 소켓과 연결한다. 

여기까지 마치면 docker-compose가 잘 돌아간다. 

- WSL-Ubuntu 부팅 시 자동으로 이 상태가 갖춰지길 원하면 1,2를 `.bashrc`에 넣으면 된다. 
    + 단 `wsl genie -s`으로 실행한 상태가 아니라면 systemd 사용이 제한되기 때문에 아래 같은 경고 메시지를 볼 수 있다.  
    + `Failed to connect to bus: No such file or directory`

## Testrun 

- 현재 위치(대체로는 유저 홈)에 아래와 같이 docker-compose.yml 파일을 생성하자.
- 현재 위치에 `data`디렉토리를 생성하자.  

```yml
version: '3'
#
services:
    tf-gpu:
        image: tensorflow/tensorflow:latest-gpu-jupyter
        environment:
            - NVIDIA_DISABLE_REQUIRE=1
            - GRANT_SUDO=yes
            - JUPYTER_ENABLE_LAB=yes
            - JUPYTER_TOKEN=1234
        volumes:
            - "./data:/mnt/space/ml"
        ports:
            - "8888:8888"
        # deploy:
        #     resources:
        #         reservations:
        #             devices:
        #                 - driver: nvidia
        #                   device_ids: ['all']
        #                   capabilities: [gpu]
        container_name: tf_gpu
```

이제 다음을 실행하자. 

```shell
$ docker-compose up 
```

잘 실행되었다면 주피터 서버가 생성되었을 것이다. 접속 주소는 웹브라우저에서 localhost:8888을 치면 된다. 토큰(비밀번호)은 1234로 설정해두었다. GPU가 잘 돌아가고 있음을 직접 확인해보자. 노트북의 Cell을 열고 아래 내용을 실행해보자. 

```python
import tensorflow as tf
tf.config.get_visible_devices(
    device_type=None
)
```

CPU 이외에 GPU가 보이면 잘 설정된 것이다. 컨테이너 안에 담긴 fashion mnist 등의 예제를 마음껏 시험해보시라. 

yml 파일에서 눈치를 챘을지 모르겠지만, deploy 항목은 docker에서만 실행되는 항목이다. 이를 주석처리 하지 않고 podman에서 돌리면 에러가 발생한다. 

# Problems Left 

아직 해결되지 않은 이슈도 있다. 

- nvidia-container-toolkit의 호환성이 떨어지는 경우가 있는 것 같다. 
- Docker Desktop을 쓰면 윈도10의 VS Code에서 지원하는 container 접속을 통해서 바로 컨테이너 접근할 수 있다. Docker Desktop이 별도의 컨테이너를 운용했기 때문에 가능하지 않았나 싶다. 그런데 이제 WSL-Ubuntu 안에서만 컨테이너가 돌기 때문에 VS Code에서 바로 접속이 불가능해졌다. 조만간 해결책이 나오기를 기대한다. 
