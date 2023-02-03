---
title: 시작하기
author: Woen-Sug Choi
date: 2023-01-29
category: Jekyll
layout: post
---

# **ROS-Gazebo 프레임워크**
ROS-Gazebo는 로봇의 제어와 시뮬레이션에서 de-facto(실질적) 기준이 되는 오픈소스 프레임워크다.
ROS와 Gazebo 모두 [Open Robotics](https://www.openrobotics.org/)가 개발지원하고 있다.

## ROS

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Ros_logo.svg/450px-Ros_logo.svg.png" style="display:block;float:right;margin-left:10px;margin-right:5px;margin-top:5px;margin-bottom:10px;width:20%">

[ROS(Robot Operating System)](https://www.ros.org/)은 로봇의 제어와 통신을 위한 오픈소스(Open-Source) 미들웨어(서로 다른 스펙과 복잡도를 가지는 다양한 소프트웨어와 하드웨어들을 통합해 로봇 설계 및 기기와 소프트웨어간 통신을 편리하게 하는 프로그램)이다. ROS는 실시간 프레임워크는 아니나 실시간 프로그램들과 결합할 수 있다. 

<img src="https://raw.githubusercontent.com/ros-infrastructure/artwork/master/distributions/humble/HumbleHawksbill.png" style="display:block;float:right;margin-left:10px;margin-right:5px;margin-top:5px;margin-bottom:10px;width:20%">

2007년 스탠포드 대학에서 개발이 시작된 ROS는 현재 2012년 설립된 [Open Robotics](https://www.openrobotics.org/)가 개발지원하고 있다. 대규모 업데이트 버전(ROS 2)이 2017년 출시되었으며 Ubuntu와 동일한 주기로 주요 업데이트를 진행하고 있다. 현재 주요 LTS(장기간 지원 버전)은 [ROS 2 Humble Hawksbill](https://github.com/ros2/ros2/releases/tag/release-humble-20220523)이며 2022년 5월 출시되어 2027년 5월까지 5년 간 지원될 예정이다. ROS 2 출시에도 ROS의 설계적 특성상 ROS 1으로 구성된 프로그램도 ROS 2와 통신이 가능하므로 현재 많은 프로그램들이 기존의 ROS (ROS 1)으로 개발된 라이브러리들이 활용되고 있으나, ROS 1은 Noetic 버전을 마지막으로 2025년 지원이 종료될 예정이다.

ROS의 프로세스들은 각각의 관계를 Node로 표현하고 Node 간 데이터 메시지를 주고 받으며 "그래프"를 통해 관계를 나타낼 수 있다. ROS를 이용해 구현 가능한 Node 간 통신방식은 총 3가지 방식(i.e. Service를 이용한 동기식 통신방식, Topic을 이용한 비동기식 데이터 스트리밍, 그리고 Parameter Server를 이용한 데이터 저장)이 있다.

ROS의 Node들은 각각 서로 다른 운영체제(Windows, Linux, Mac OS X), 프로그래밍 언어(C++, Python, MATLAB, Java, Javascript)로 구성되어도 Node 간 통신이 가능하며, 프로세스들은 Package 또는 Stack으로 그룹될 수 있다.


## Gazebo

<img src="https://classic.gazebosim.org/assets/masthead-0bd44817978df8069f427d8ca1657998789065a2b242edfd1a3d8ab4a329dd4c.png" style="display:block;float:right;margin-left:10px;margin-right:5px;margin-top:5px;margin-bottom:10px;width:20%">

[Gazebo](https://gazebosim.org)는 [ODE(Open Dynamics Engine)](https://bitbucket.org/odedevs/ode/src/master/) 물리엔진과 [OGRE](https://www.ogre3d.org/)와 OpenGL 렌더링엔진을 기반으로 하는 오픈소스(Open-Source) 3차원 로봇 시뮬레이터이다. ROS와 마찬가지로 [Open Robotics](https://www.openrobotics.org/)가 개발지원한다. 기본적으로 제공하는 센서와 모델들을 활용 가능하며, C++ 를 이용해 [플러그인을 개발](https://gazebosim.org/api/gazebo/3.0/resources.html)할 수 있다.

<img src="https://user-images.githubusercontent.com/5751272/135693256-e300885b-51be-40b2-bf81-de14849ee7d0.jpeg" style="display:block;float:right;margin-left:10px;margin-right:5px;margin-top:5px;margin-bottom:10px;width:20%">

2004년부터 [Player Project](https://playerstage.sourceforge.net/)로 개발되었으나, 2012년 Open Robotics에 의해 별도 프로젝트로 독립하였다. 현재 최신 LTS(장기지원 버전)은 2021년 출시한 [Gazebo Fortress](https://github.com/gazebosim/gz-sim/releases/tag/ignition-gazebo6_6.0.0)로 2026년까지 지원될 예정이다. Gazebo의 버전은 크게 [Gazebo](https://gazebosim.org/)와 [Gazebo Classic](https://classic.gazebosim.org/)(2020년 1월 출시된 Gazebo 11이 LTS(장기 지원 버전)으로 2025년 1월까지 5년간 지원 후 종료될 예정)으로 구분된다. 초기 Gazebo(비 Classic 버전)는 Ignition이란 이름으로 기존의 Gazebo (Classic 버전)와 구분해 개발되었으나, Gazebo로 명칭을 변경함에 따라 기존의 Gazebo가 Gazebo Classic으로 변경되었다. (구버전 (Gazebo, Ignition) -> 현재 (Gazebo Classic, Gazebo))

Gazebo는 다양한 로봇대회에서 시뮬레이션에 활용되고 있다.
- [Robotics Challenage](https://bitbucket.org/osrf/drcsim) (미국 고등연구계획국 주관, 2012-2015)
- [NASA Space Robotics Challenge](https://bitbucket.org/osrf/srcsim) (2016-2017)
- [Toyota Prius Challenge](https://bitbucket.org/osrf/priuscup/src/default/) (2016-2017)
- [ARIAC](https://bitbucket.org/osrf/ariac/wiki/Home) (미국표준기술연구소 주관, 2016-2020)
- [Service Academy Swarm Challenge](https://github.com/osrf/uctf) (미국 고등연구계획국 주관, 2016-2017)
- [Subterranean Challenge](https://bitbucket.org/osrf/subt/wiki/Home) (미국 고등연구계획국 주관, 2018-2021)
- [Virtual RobotX Competition](https://github.com/osrf/vrx) (미국 해군연구소, 미해군대학원 주관, 2019-)

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


#### 외장그래픽 드라이버 설정

Install NVIDIA Grahics Driver for WSL2 Docker

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
[2]: 