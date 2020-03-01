---
layout: post
title:  "네이버 클라우드 서버 세팅"
date:   2020-01-03 21:25:36 +0900
---

오늘 네이버 클라우드 무료 서버인 Micro 서버를 생성하여 Ubuntu VNC를 세팅했다.
클라우드 서버 발급은 아래 링크 참고<br>
[네이버 클라우드 무료 서버 이용하기](https://blog.naver.com/nieah914/221609709142 "네이버블로그 - 피드백맨님")

위 링크를 참고하여 Micro 서버 발급 후 기본적으로 우분투 패키지 업데이트 진행.
sudo apt update

후에 gui module 설치를 위해 tasksel을 설치한다.<br>
sudo apt-get install tasksel<br>
tasksel 설치 후 ubundu gui module을 설치한다.<br><br>

sudo tasksel install ubuntu-desktop<br>
아래 화면과 같이 ubuntu-desktop이 설치된다. 시간은 꽤 소요되는듯
![Image]( {{base.url}} /assets/images/ubundu-desktop_install.png)

설치가 완료되면 별다른 이벤트 없이 아래와 같이 install이 한줄 나온다.

![Image]( {{base.url}} /assets/images/ubuntu-desktop_installed.png)

ubuntu-desktop이 설치된 후 gdm3를 실행해야 하는데, 본인이 진행하는 서버에는 설치가 되있지 않아서 gdm3도 추가로 설치해준다.
<br>
sudo apt-get install gdm3

