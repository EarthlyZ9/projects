# PinTalk

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

![pycharm badge](https://img.shields.io/badge/PyCharm-000000?style=flat-square&logo=PyCharm&logoColor=white)

![python badge](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white)
![django badge](https://img.shields.io/badge/Django-092E20?style=flat-square&logo=Django&logoColor=white)
![redis badge](https://img.shields.io/badge/Gunicorn-499848?style=flat-square&logo=Gunicorn&logoColor=white)
![nginx badge](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=NGINX&logoColor=white)

![mysql badge](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white)
![docker badge](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white)
![aws badge](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazon-aws&logoColor=white)

![logo](https://github.com/EarthlyZ9/projects/assets/89679621/a9037b5a-1b20-429d-a7a5-6c2a527fbcef)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

[깃헙 레포 바로가기](https://github.com/EarthlyZ9/PinTalk-API)



### 💡 Summary
다수의 웹페이지들에서 빠른 문의와 방문자와의 소통을 위해 우측 하단에 채팅 위젯을 제시하고 있다.
자체적으로 구현하는 서비스들도 있지만, 디자인 커스텀이 가능한 채팅 위젯과 별도의 채팅 서버를 제공해주는 서비스들도 있다.
이런 서비스들은 보통 유료이며, 사업자 인증을 받아야하는 경우도 있다. (ex. 카카오 비즈톡) 비슷한 서비스를 제공하지만,
무료이고 개발을 하는 누구나 본인이 제작한 웹사이트에 쉽게 적용할 수 있는 채팅 위젯이 있으면 좋겠다는 아이디어에 착안하여 
PinTalk 프로젝트를 기획하고 진행하게 되었다. 
내부적으로 PinTalk 의 웹소켓 서버에 연결시켜주는 채팅 위젯과 채팅창은 NPM 패키징을 통해 누구나 접근할 수 있도록 기획하였고, 
해당 패키지를 사용하길 희망하는 개발자들은 PinTalk 메인 웹페이지에 접속하여 간단하게 회원가입만 하면 API Key 를 발급받아
패키지를 사용 권한을 얻을 수 있으며 웹페이지의 채팅 대시보드를 통해 채팅방을 관리하고 방문객들과 소통할 수 있다.


#### 🗓 2023.01.02 ~ 2023.04.30

#### 👥 Collaborators
본 프로젝트는 총 4명이서 함께 작업한 결과물이다. (디자이너 1명, 웹페이지 FE 1명, NPM Package 개발 FE 1명, 백엔드 API 1명)

나는 백엔드 API 개발을 맡았다.

#### 📋 Features
1) 무상태 서비스 - wsgi
   - 회원가입, 비밀번호 변경 및 초기화, 프로필 수정 등과 관련된 HTTP API 개발

2) 상태서비스 - asgi
   - Daphne 를 사용하여 asgi 와 wsgi 요청을 구분하여 처리
   - Django Channels 패키지와 웹소켓 프로토콜을 이용한 메시지 전송 및 온라인 여부 확인
   - redis zset 을 이용한 메시지 저장
   - 여러 대안을 고려하였으나, Redis 에 최신 메시지를 저장하고 비동기적으로 MySQL 에 저장하는 방식으로 구현
   - *게스트와 호스트의 핀톡 서버 접속 로그*
![video](https://github.com/EarthlyZ9/projects/assets/89679621/e911f11a-e6cf-435e-a637-f1508dd1be85)

3) 배포
- EC2 + Docker Compose (Nginx, Redis, Daphne + Django, MySQL 컨테이너)


[PinTalk 기획 및 개발에 대한 기록들](https://notion.earthlyz9.dev/django/chat-service)

#### 🛠 Tech Stack
* Python, Django Rest Framework, Daphne, Nginx, MySQL, Redis, Django Channels
* Deployment: AWS S3, EC2, Docker Compose

#### 🔗 URLS
- ~~[PinTalk 서비스 바로가기]()~~ (도메인 만료됨😥)

---

### 📌 Trouble Shooting
jwt 로 무상태성을 유지하고 있었기 때문에 HTTP 프로토콜에서 웹소켓 프로토콜로의 업그레이드 요청 시 인증을 할 수 있는 별도의 수단이 필요했다. 
query string 으로 jwt token 을 보내는 방식을 선택하였는데 
nginx 에서 토큰의 온점을 delimiter 로 간주하는 기본 동작 때문에 토큰을 제대로 인식하지 못하는 문제에 직면했다. 
로컬에서 테스트를 할 때에는 이 문제가 나타나지 않아 그 원인을 알기 어려웠으나 ec2 환경에서 
nginx 의 로그 파일을 보고 오류를 추적하여 온점 delimiter 때문임을 알 수 있었다. 
온점을 다른 기호로 대체하여 보내는 방식으로 token 을 검사할 수 있었다.


### 📌 Achievements
1) 웹소켓 프로토콜에 대한 이해
2) Django Channels 와 Redis Layer 에
   대한 이해
3) Redis zset 에 대한 이해와 score 의 활용

### 📌 Thoughts
내용이 길어서 다른 곳에 옮겨서 기재함!

[PinTalk, 채팅 서비스 개발기](https://notion.earthlyz9.dev/thoughts/pintalk)
