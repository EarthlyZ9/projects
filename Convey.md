# Convey

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

![pycharm badge](https://img.shields.io/badge/PyCharm-000000?style=flat-square&logo=PyCharm&logoColor=white)

![python badge](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white)
![django badge](https://img.shields.io/badge/Django-092E20?style=flat-square&logo=Django&logoColor=white)
![nginx badge](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=NGINX&logoColor=white)
![gunicorn badge](https://img.shields.io/badge/Gunicorn-499848?style=flat-square&logo=Gunicorn&logoColor=white)
![pytest badge](https://img.shields.io/badge/Pytest-0A9EDC?style=flat-square&logo=Pytest&logoColor=white)

![mysql badge](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white)
![docker badge](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white)
![aws badge](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazon-aws&logoColor=white)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white?link=https://github.com/linda2927/bruteforce)

[깃헙 레포 바로가기](https://github.com/PI304/Convey-API)



### 💡 Summary
PI Lab 에서 진행한 실험적인 프로젝트. 피험자들을 대상으로 한 연구 설문을 수합하는 과정을
모바일 어플리케이션을 통해 간편화하는 것을 목적으로 한다. 해당 프로젝트는 웹페이지와 앱으로 구성되어
있으며, 설문을 등록하고 결과를 확인하는 관리자 페이지는 웹, 피험자들이 이용하는 설문 어플리케이션은
앱으로 구현하였으며 협력 연구소와 함께 실제 설문으로 테스트까지 진행해보았다. 
~~실제로는 공인된 설문지를 웹상에서 배포하는 것과 관련된 문제 때문에 그 이상 진행되지 못했다.~~


7 ~ 8 종류 가량의 설문 문항 유형이 있었고 (ex. likert) 유형별로 문제 지문과, 추가 지문,
선택 선지, 주관식 서술란 등을 구성해야했으며, API 로 주고 받는 JSON 객체가 상당히 크고 depth 가 
깊어서 DB 테이블 설계와 Nested Object 를 다뤄야한다는 측면에서 도전적인 과제였다.

여러 개의 소설문이 하나의 패키지를 이루는 구조이며, 그 안에서도 특정 대주제와 소주제에 따라 부가적인 정보들이 덧붙여진다.
정리하면 아래와 같은 depth 를 갖게된다.

> Survey Package > Package Parts > Package Subjects > Surveys > Sections

#### 🗓 2023.02.20 ~ 2023.03.30

#### 👥 Collaborators
본 프로젝트는 총 3명이서 함께 작업한 결과물이다. (안드로이드 어플리케이션 1명, 관리자 웹페이지 FE 1명, 백엔드 API 1명)

나는 백엔드 API 개발을 맡았다.

#### 📋 Features
1) Authentication
   - http-only secure cookie refresh token, blaklist 처리를 통한 토큰 탈취에 대한 위험 관리
   - 모바일 앱과 개인 정보 통신 시 AES 암/복호화 처리

2) DB 설계 및 쿼리 작성
   - 7 ~ 8 종류 가량의 설문 문항 유형이 있었고 (ex. likert) 유형별로 문제 지문과, 추가 지문, 선택 선지, 주관식 서술란 등을 구성, API 로 주고 받는 JSON 객체가 상당히 크고 depth 가 깊어서 Nested Object 로 다룸
   - ORM 최적화 수행 및 Silk middleware 를 이용한 모니터링
   - 소설문 생성/삭제, 소설문 내 다양한 문제 유형 및 선지 구성, 설문 패키지 생성 및 다수의 소설문 연결

3) 데이터 엑셀 export
   - Eager loading 을 통한 데이터 fetching
   - 설문 패키지 구성과 응답을 xlsx 형태로 파싱하여 file download 기능 구현

4) 배포
   - EC2 + Docker Compose (Nginx, Gunicorn + Django, MySQL 컨테이너)

#### 🛠 Tech Stack
* Python, Django, Gunicorn, Nginx, MySQL, PyTest
* Deployment: AWS S3, EC2, Docker Compose

#### 🔗 URLS
- ~~[Convey 서비스 바로가기]()~~ (도메인 만료됨😥)

---

### 📌 Trouble Shooting
1:N 관계가 연쇄적으로 이어져 있는 nested 구조의 데이터를 fetch 하여 파일로 파싱하는 과정에서 
쿼리가 불필요하게 많이 발생하는 현상을 포착하였다. silk middleware 를 사용하여 모니터링 해본 결과, 
설문 응답 결과를 파싱하는 과정에서 108개의 쿼리가 발생하고 있다는 것을 확인하였고, 
eager loading 을 통해 12 개까지 감소시킬 수 있었다.

### 📌 Achievements
1) Nested Object 의 효율적인 쿼리 - ORM 최적화
2) AES 암호화 알고리즘에 대한 이해
3) depth 가 깊은 DB 설계에 대한 고민
4) pytest 를 이용한 통합 및 단위 테스트 이해 및 활용

### 📌 Thoughts
반환해야하는 데이터가 Nested 된 형태가 많아서 DB Diagram 설계할 때나 쿼리를 작성할 때 고민을 많이 할 수 밖에
없었던 프로젝트였다. Eager loading 을 적절하게 사용해서 큰 객체를 반환해야하는 경우가 많았기 때문에
DRF 의 ```prefetch_related()``` 나 ```select_related()``` 을 적극적으로 사용해볼 수 있는 
기회가 되었다. 

이 프로젝트를 하면서 가장 힘들었던 건, 데이터 구조가 복잡하고 개발 기간이 굉장히 짧아서 (픽스까지 한달 조금 넘게 걸렸지만, 실제 개발은 2주 정도)
그 안에 명세를 확립하고 효과적으로 소통하기가 굉장히 어려웠다는 점이다. 프로젝트에 굉장히
빠르게 투입이 되었고, 준비 기간 없이 바로 개발에 들어가는 바람에 문서화되어 있는 명세가 없어서 FE 개발자, 앱 개발자, BE 개발자들이
각자 개발을 하면서 혼란스럽거나 다시 정의해야하는 부분들이 많았다. 
백엔드 API 를 소비하는 쪽이 웹과 앱 두 쪽이다 보니까 양쪽 개발자들과 소통해야할 일이 
굉장히 많았는데, 이 과정에서 소통이 지연되는 경우도 있었다. 이 프로젝트를 계기로
바람직한 프로젝트 매니징과 개발 워크플로우에 대해 많은 고민들을 하게 된 것 같다.
그리고 개인적으로도 코드를 작성하는 것 외에도 문서화와 문서들의 정리에 대해서 시간을 좀 더 할애하고
신경써야겠다는 생각이 들었다...!
