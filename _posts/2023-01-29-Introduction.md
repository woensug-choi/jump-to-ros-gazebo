---
title: 시작하기
author: Woen-Sug Choi
date: 2023-01-29
category: Jekyll
layout: post
---

# **ROS-Gazebo 프레임워크**
ROS-Gazebo 프레임워크는 로봇 시뮬레이션에서 de-facto (실질적) 벤치마크의 기준이 되는 프레임워크로 자리잡고 있다.

## ROS
ROS 는 Robot Operating System의 약자로 로봇어플리케이션을 구성하는 툴과 라이브러리들을 포함하는 프로그램들 패키지 이다.

## Gazebo
Gazebo 는 물리엔진을 이용한 로봇의 가상화 실험을 간능하게 하는 
가상환경 시뮬레이터로 오픈소스이다.

# **ROS-Gazebo 설치하기**

## 설치환경 준비
ROS와 Gazebo 모두 윈도우와 리눅스 어느 운영체제에서도 설치 가능하나 각 프로그램이 리눅스 환경에서 개발되었다는것을 고려할 때 리눅스 환경에 설치하는 것이 자연스럽다. 

따라서 ROS-Gazebo 프레임워크를 설치하기 위해서는 리눅스 환경이 필요하다. 리눅스 환경을 구성하는 방법은 아래와 같이 2가지 방법이 있다.
- 네이티브 리눅스 환경 구성 (듀얼부팅, 또는 포맷 후 리눅스만 설치)
- **(추천!)** 윈도우에 WSL[^1]을 이용한 리눅스 가상환경 구성

**일반적으로 가상환경은 성능저하가 발생하나, WSL은 성능저하 없이[^1] 리눅스 환경을 구성할 수 있다.**

[^1] WSL(Windows Subsystem for Linux)
- 윈도우에서 네이티브로 리눅스 실행파일을 실행하기 위한 호환성 하위 계층
    - 윈도우에서 리눅스를 사용하기 위한 도구
    - 듀얼부팅 설정 불필요. 가상머신화 불필요. 빠른 속도 장점
- 2016년에 WSL처음 등장 2019년에 WSL2 등장. Microsoft 재정기반으로 진행되고 있어서 개발속도가 매우 빠름
    - 예를들어 Ubuntu에서 [X.org](http://X.org) (그래픽 표현 시스템)을 차세대 Wayland로 21.04 버전에서 변환했고 22.04 (2022년 4월) 부터 배포했는데, WSL은 이미 2020부터 Wayland 기반
    - 개발문화도 매우 개방적이로 스타트업 분위기여서 개발자가 자기 블로그/유투브에 개발내용 공개하고 개발자들 환호하고 댓글달고 함 (이거보고 마소 주식 삼)

[^2] 파일의 읽기쓰기 성능에 제한이 있으나 계산속도에서는 네이티브와 차이가 거의 없다.

### 윈도우 WSL 환경 준비
윈도우 11부터는 WSL을 설치하기 위한 환경이 이미 구성되어 있다. 윈도우 10의 경우 버전 2004 (빌드 19041) 이상이어야 하며 이전 버전의 경우 [수동 설치](https://learn.microsoft.com/ko-kr/windows/wsl/install-manual) 해야 한다.

#### WSL2 설치

윈도우 시작버튼을 오른쪽 클릭해 Windows PowerShell(관리자) 실행을 클릭해 윈도우 터미널을 관리자 모드로 실행하고 다음 명령어를 입력한 다음 컴퓨터를 다시 시작한다.

```bash
wsl --install Ubuntu-22.04
```

재시작 후, 다시 Windows PowerShell(관리자)에서 다음 명령어를 입력해 Ubuntu 22.04를 실행하는 WSL의 버전을 2로 설정한다.

```bash
wsl --set-version Ubuntu-22.04 2
```

* (Recommend) Install Windows Terminal to access Ubuntu in WSL2
    - [Windows Terminal (Microsoft Store)](https://www.microsoft.com/ko-kr/p/windows-terminal/9n0dx20hk701)


### 외장그래픽 드라이버 설정

(For GPU version) Install NVIDIA Grahics Driver for WSL2 Docker

    - If you are running only with CPUs, you do not need this
    - Download and install NVIDIA Driver for WSL2
        - [CUDA on Windows Subsystem for Linux (WSL)](https://developer.nvidia.com/cuda/tf_wsl)
    - Check configuration for NVIDIA Graphics Card
        - Run this command inside Ubuntu 20.04 in WSL2

        ```bash
        glxinfo | grep OpenGL
        ```

        You should see something like following,

        ```bash
        OpenGL vendor string: Microsoft Corporation
        OpenGL renderer string: D3D12 (NVIDIA GeForce GTX 1660 Ti)
        ```

        If NOT, do

        ```bash
        sudo add-apt-repository ppa:kisak/kisak-mesa && sudo apt-get update && sudo apt dist-upgrade
        ```


## 옵션 1. Ubuntu에 직접설치

### - ROS 설치
ROS 2를 설치한다.

### - Gazebo 설치
Gazebo Garden을 설치한다.

## 옵션 2. Docker로 설치





[1]: https://pages.github.com