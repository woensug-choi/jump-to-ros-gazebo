---
title: ❑ ROS-Gazebo란?
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