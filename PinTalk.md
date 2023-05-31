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

![logo](https://github.com/EarthlyZ9/projects/assets/89679621/2412b186-57f8-4456-93ad-345ec1605f70)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

[깃헙 레포 바로가기](https://github.com/PI304/PinTalk-API)



### 💡 Summary
다수의 웹페이지들에서 빠른 문의와 방문자와의 소통을 위해 우측 하단에 채팅 위젯을 제시하고 있다.
자체적으로 구현하는 서비스들도 있지만, 디자인 커스텀이 가능한 채팅 위젯과 별도의 채팅 서버를 제공해주는 서비스들도 있다.
이런 서비스들은 보통 유료이며, 사업자 인증을 받아야하는 경우도 있다. (ex. 카카오 비즈톡) 비슷한 서비스를 제공하지만,
무료이고 개발을 하는 누구나 본인이 제작한 웹사이트에 쉽게 적용할 수 있는 채팅 위젯이 있으면 좋겠다는 아이디어에 착안하여 
PinTalk 프로젝트를 기획하고 진행하게 되었다. 
내부적으로 PinTalk 의 웹소켓 서버에 연결시켜주는 채팅 위젯과 채팅창은 NPM 패키징을 통해 누구나 접근할 수 있도록 기획하였고, 
해당 패키지를 사용하길 희망하는 개발자들은 PinTalk 메인 웹페이지에 접속하여 간단하게 회원가입만 하면 API Key 를 발급받아
패키지를 사용 권한을 얻을 수 있으며 웹페이지의 채팅 대시보드를 통해 채팅방을 관리하고 방문객들과 소통할 수 있다.
보다 자세한 기획은 아래 링크 참고!

[PinTalk 기획](https://earthlyz9-dev.oopy.io/django/chat-service)


[PinTalk 웹사이트](https://pintalk.app)


*메인 웹사이트는 여전히 픽스가 진행되고 있으며, PinTalk NPM Package 는 보수 중에 있습니다.*


**게스트와 호스트의 핀톡 서버 접속 로그**


![핀톡 서버 시연](https://github.com/EarthlyZ9/projects/assets/89679621/e911f11a-e6cf-435e-a637-f1508dd1be85)


#### 🗓 Collaborators
본 프로젝트는 총 4명이서 함께 작업한 결과물이다. (디자이너 1명, 웹페이지 FE 1명, NPM Package 개발 FE 1명, 백엔드 API 1명)

나는 백엔드 API 개발을 맡았다.


#### 🗓 2023.01.02 ~ 2023.04.30

### 📋 Features
* 채팅을 위한 웹소켓 (상태 서비스)
* Redis 를 이용한 최근 메시지 저장
* HTTP API 를 이용한 무상태 서비스
* 자세한 내용은 아래 링크 참고

[PinTalk 개발기](https://earthlyz9-dev.oopy.io/django/chat-service)


### 🛠 Tech Stack
* Python, Django Rest Framework, Daphne, Nginx, MySQL, Redis, Django Channels
* Deployment: AWS S3, EC2, Docker Compose


### 📌 Takeaways
내용이 길어서 다른 곳에 옮겨서 기재함!
[PinTalk, 채팅 서비스 개발기](https://earthlyz9-dev.oopy.io/thoughts/pintalk)

***
