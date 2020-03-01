---
layout: post
title:  "docker를 통한 jenkins 설치"
date:   2020-03-01 20:50:36 +0900
---

지난 포스트에서 docker CE를 설치했다. 이번엔 docker를 이용해 jenkins를 설치해보자.

<h2>1. Jenkins 이미지 받기</h2>
Docker Hub에서 pull 명령어를 사용해 jenkins 이미지를 받을 수 있다.
**docker pull jenkins/jenkins:lts<br>**
<h2>2. Jenkins 컨테이너 실행하기</h2>
pull이 완료되면 **docker images**를 입력해 jenkins/jenkins가 pull 되었는지 확인한다.
<br>
![Image_1]( {{base.url}} /assets/images/jenkins_jenkins.png)
<br>
확인 후 아래 명령어를 사용해 jenkins 이미지를 컨테이너로 실행한다.<br>
**docker run -d -p 8181:8080 -v /jenkins:/var/jenkins_home --name jm_jenkins -u root jenkins/jenkins:lts**
<br>
<br>
<h2>3. 브라우저로 접속하여 설치작업 계속하기</h2>
실행후 localhost의 포워딩한 8181 포트로 접속하면 jenkins unlock page가 나타난다.<br>
터미널에 아래 명령어를 사용하여 installation password를 복사해 Admin password를 입력한다.<br>
**docker exec jm_jenkins cat /var/jenkins_home/secrets/initialAdminPassword**
<br><br>
입력 후 Install suggested plugins를 클릭하여 권장 플러그인들을 설치한다.<br>
설치가 완료되면 아래와 같이 초기 계정 생성창이 뜬다. <br>
![Image_2]( {{base.url}} /assets/images/jenkins_first_admin_user.png)<br>

