# BK Nutrition

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

![pycharm badge](https://img.shields.io/badge/PyCharm-000000?style=flat-square&logo=PyCharm&logoColor=white)

![python badge](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white)
![fastapi badge](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=FastAPI&logoColor=white)
![jinja badge](https://img.shields.io/badge/Jinja-B41717?style=flat-square&logo=Jinja&logoColor=white)
![mysql badge](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white)

![nginx badge](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=NGINX&logoColor=white)
![docker badge](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white)

![aws badge](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazon-aws&logoColor=white)

![logo](https://user-images.githubusercontent.com/89679621/226145943-074ce81c-ebdb-459f-a21e-b0e8968f3062.png)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

> **해당 프로젝트의 Repo 는 비공개입니다.**



### 💡 Summary
연세대학교 식품영양학과의 BK21 웰니스 융합인재 양성팀 (연구실) 의 홈페이지를 새단장하는 프로젝트로,
백엔드 API 와 리소스 관리를 위한 관리자 페이지 구현을 맡았다. 개발에 주어진 기간이 10일 정도로
굉장히 짧았고 개발 스코프도 크지 않았기 때문에 주로 사용하는 Django REST Framework 가 아닌
FastAPI 를 선택하였으며, 빠른 프론트엔드 개발을 위해 Jinja 와 sqladmin 이라는 패키지를 사용했다.

#### 🗓 2023.02

#### 👥 Collaborators
본 프로젝트는 총 2명이서 함께 작업한 결과물이다. (프론트엔드 1명, 백엔드 & 프론트엔드 1명) 

나는 관리자 페이지의 프론트엔드와 백엔드 API를 맡아 진행했다.

#### 📋 Features
* 관리자 페이지/리소스 관리: 웹사이트에 업로드하는 모든 리소스를 CRUD 하는 공간
* 리소스 전달을 위한 API

#### 🛠 Tech Stack
* Frontend: Jinja
* Backend: MySQL, FastAPI, SqlAlchemy, Alembic, Uvicorn
* Deployment: Docker Compose, Nginx, EC2

---

### 📌 Achievements
1) Jinja Template 에 대한 이해
2) [파이썬 패키지 구조 뜯어보기](https://notion.earthlyz9.dev/thoughts/deep-dive-python-package)

### 📌 Thoughts
이번 프로젝트에서 백엔드 스택을 주로 사용하는 DRF 가 아닌 FastAPI 를 선택한 이유는
FastAPI 가 가진 손쉬운 OpenAPI (Swagger) 및 JSON Schema 관련 기능 때문이었다.
애초에 endpoint 가 많지 않아 FastAPI 를 사용하면서 '빠르게' 개발할 수 있을 것 같다는
생각이 들었다. 그런 생각 때문인지 FastAPI 가 개발 스코프가 작은 프로젝트를 빠르게 
개발하는 데에 유용할 거라는 생각이 무의식 중에 든 것 같다. 
그런데 이번에 FastAPI 를 제대로 사용해보면서 오히려 대규모 프로젝트에 어울린다는 생각이 들었다.
일단, 타입 어노테이션이 아주 강력하게 적용되어 있다는 점에서 (Pydantic 을 프레임워크에서 적극적으로 활용하고 있음)
다수의 인원이 프로젝트에 참여할 때 굉장히 유용할 것 같다고 생각했다. Django 의 경우, 타입 힌팅을
잘 사용하지 않는 경향이 있고, 실제로 Django 의 많은 부분이 C로 구현되어 있어 Mypy에서 타입 검사를 할 수 없는 경우가 많다고 한다
(그래서 django-stub, djangorestframework-stub 같은 걸 쓰는 거고)

타입 어노테이션 뿐만 아니라 ASGI 를 기본적으로 사용하기 때문에 대규모 트래픽에 좀 더 최적화 되어 
있다는 점도 내가 처음에 FastAPI 에 대해 잘못된 인식을 가지고 있었음을 증명한다. Django 의 메인 홈페이지에 들어가보면,
아래와 같이 적혀있는 걸 볼 수 있는데, 이는 결국 Django 의 목적이 '쉽고 간결한' 데에 있다는 것을 알 수 있다.
> Django makes it easier to build better web apps more quickly and with less code.

반면에 FastAPI 의 경우, 아래와 같이 '성능' 에 대한 부분이 가장 먼저 강조되어 있는 걸 느낄 수 있다.

> FastAPI framework, high performance, easy to learn, fast to code, ready for production

각 프레임워크가 내세우고 있는 메인 메시지 만으로도 그 목적성과 성격이 다르다는 걸 알 수 있다는 게
매우 흥미로웠다. 능숙하게 다룰 수 있는 스택을 보다 다양화해서 프로젝트의 성격에 맞는 스택을 선택할 수 있는
능력있는 개발자가 되고 싶다는 생각이 들었다.


