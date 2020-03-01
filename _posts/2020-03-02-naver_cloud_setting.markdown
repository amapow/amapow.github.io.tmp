---
layout: post
title:  "네이버 클라우드 서버 세팅"
date:   2020-03-01 17:25:36 +0900
---

오늘 네이버 클라우드 무료 서버인 Micro 서버를 생성하여 Ubuntu VNC를 세팅했다.
클라우드 서버 발급은 아래 링크 참고<br>
[네이버 클라우드 무료 서버 이용하기](https://blog.naver.com/nieah914/221609709142 "네이버블로그 - 피드백맨님")

위 링크를 참고하여 Micro 서버 발급 후 기본적으로 우분투 패키지 업데이트 진행.
<br>
**sudo apt update**

후에 gui module 설치를 위해 tasksel을 설치한다.<br>
**sudo apt-get install tasksel**<br><br>


tasksel 설치 후 ubuntu gui module을 설치한다.<br>
**sudo tasksel install ubuntu-desktop**<br>
아래 화면과 같이 ubuntu-desktop이 설치된다. 시간은 꽤 소요되는듯
![Image_1]( {{base.url}} /assets/images/ubundu-desktop_install.png)

설치가 완료되면 별다른 이벤트 없이 install이 한줄 표시된다.

ubuntu-desktop이 설치된 후 gdm3를 실행해야 하는데, 본인이 진행하는 서버에는 설치가 되있지 않아서 gdm3도 추가로 설치해준다.
<br>
**sudo apt-get install gdm3**

gdm3 설치 후 gdm3를 실행한다.

**sudo systemctl enable gdm3**
**sudo systemctl start gdm3**

gdm3 실행이 확인 되었으면 vnc4server를 설치한다.<br>
**sudo apt-get install vnc4server**

vnc4server 설치 후 실행<br>
**vnc4server**

vnc4server 실행 후 **netset -tnlp**를 입력하여 확인해보면 5901 port로 Xvnc가 실행된 것을 확인할 수 있다.<br>
![Image_3]( {{base.url}} /assets/images/netstat-tnlp.png)

그 후 이용하는 클라우드 서버에 5901 포트를 포워딩 후 vnc viewer를 이용해 접속하면 아래와 같이 접속이 잘 됨을 확인할 수 있다.
![Image_3]( {{base.url}} /assets/images/vnc_viewer.png)

계속해서 접속할 수 없다는 에러로 애를 먹었는데, 네이버 클라우드의 경우 ssh 접속용 IP가 아닌 공인IP를 입력해야 접속이 가능하다.

다음 포스팅은 docker와 jenkins 설치로 뵙겠다.

