# BisTime

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


![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

[깃헙 레포 바로가기](https://github.com/EarthlyZ9/BisTime-API)


### 💡 Summary
학회 팀빌딩 과정에서 제일 크게 느낀 것은 일정 관리와 타임 매니지먼트가 정말 어렵다는 점이었다. 
특히, 규칙적인 일정이 있는 직장인 아닌 각기 다른 일정에 따라 생활하는 학부생들 간의 일정을 조율하는 일이란
쉬운 일이 아니다. 'When2Meet' 나 'LettuceMeet'와 같이 이러한 그룹 스케줄링을 돕는 서비스들이 이미 있지만
사용의 편의성을 보다 높이고, 보다 체계적으로 '팀' 단위의 타임 매니지먼트를 도울 수 있는 툴을 만들고자 
BisTime 프로젝트를 기획하게 되었다. 


### 👀 BisTime 소개
BisTime (비즈타임, 비는 시간,,,) 은 그룹 스케줄링을 돕는 기존 서비스들의 단점을 파악하고 이를 보완하고자 하는 프로젝트이다.
대표적으로 많이 쓰이는 서비스에는 When2Meet 와 LettuceMeet 가 있는데 둘 다 사용성이 떨어진다고 느꼈고 (특히 모바일 환경에서)
계속 사용하고 싶은 서비스라는 느낌이 들지 않았다. 또한 팀 매니지먼트에 필수적이라고 볼 수 있는 '팀원의 리소스 및 일정 파악' 이라는
목적을 이룰 수 있도록 돕는 툴로서도 기능했으면 좋을 것 같다는 생각이 들었다. 

BisTime 개발 프로세스는 Phase 1 과 Phase 2 로 나뉘어진다. Phase 1 의 목적은 기존의 서비스들이 구현하고 있는
빠르고 쉬운 스케줄링 이라는 컨셉을 따르되, 모바일 프렌들리한 UI 를 목표로 작업했다. Phase 2 는 본격적으로 '팀' 단위로 사용할 수 있는
유사-헙엽툴로서의 역할을 할 수 있도록 관련 기능들을 추가할 예정이다. Phase 2 작업의 목표는 여러 명이 지속적으로 타임 매니징을 위해
사용할 수 있는 툴로서 기능하면서, 동시에 이런 웹서비스들의 근본적인 목표인 '쉽고 빠른 스케줄링' 에서 벗어나지 않는 것이다.

*BisTime 프로젝트는 현재 Phase 1 이 완료되고, Phase 2 를 준비하고 있는 단계입니다. Phase 2 에 해당하는 API 는 완성되어 있으나 프론트엔드 개발자의 공백으로
잠시 진행이 중단되어 있는 상태입니다.*

#### 🗓 2023.01 ~ 2023.03

#### 👥 Collaborators
본 프로젝트는 총 2명이서 함께 작업한 결과물이다. (UI 디자인 및 프론트엔드 개발 1명, 기획, 프로젝트 총괄 및 백엔드 API 개발 1명)

나는 프로젝트 기획과 총괄, 그리고 백엔드 API 개발을 맡았다.

#### 📋 Features
1) 모임 및 일정 생성/수정/삭제
   - 모임 하위에 모임날짜 후보와 모임날짜에 따라 개인 일정을 추가할 수 있는 DB 구조 설계
   - 일정의 경우 하루를 48개의 블럭으로 나누어 bytearray 로 저장 (전체 availability 의 빠른 계산을 위함)

2) 팀 및 하위 일정 생성/수정/삭제
   - 48 X 7 의 bmp 파일로 개인 일정을 AWS S3 에 저장
   - 여러 bmp 파일을 겹쳐 전체 availability 파악 방식

3) Next.js FE 어플리케이션 배포자동화 (CI/CD)
   - GitHub Actions 를 통해 Docker Hub 에 빌드한 이미지를 push 하고 ec2 에서 pull 하여 배포하는 방식
   - macos 에서 이미지 빌드 시, ec2 ubuntu 에서 작동시킬 수 없어 Docker Buildx 를 이용하여 linux/amd64 로 빌드

4) Backend API 배포
   - EC2 + Docker Compose (Nginx, Django, MySQL 컨테이너)


#### 🛠 Tech Stack
* Python, Django DRF, Gunicorn, Nginx, MySQL, PyTest
* Deployment: GitHub Actions, AWS EC2, Docker, Docker Compose

#### 🔗 URLS
- ~~[BisTime 서비스 바로가기]()~~ (도메인 만료됨😥)

---

### 📌 Trouble Shooting
타입힌팅을 도입하고자 MyPy 를 사용하였지만 실제 Django 프로젝트에 엄격한 타입힌팅을 적용하기가 어려웠다. 
이는 FastAPI 와는 다르게, Django 의 경우 처음 설계될 때 타입힌팅이 존재하지 않아 이를 적극 고려하여 설계된 것이 아니기도 하고
타입힌팅과 별개로 작동하는 자체 ORM을 사용하기 때문임을 배웠다. 
하지만 api 함수를 작성할 때 타입힌팅을 도입하면 가독성이 증가될 것이라고 생각해 부분적으로 도입하고자 했다.
이에 따라 django-stubs 와 djangorestframework-stubs 를 통해 모델 쪽 타입힌팅을 생략할 수 있었다. 
이 경험을 통해 프로젝트나 프레임워크의 특성을 생각하여 타이핑 정책을 도입하는 것이 바람하다는 배움을 얻을 수 있었다.

### 📌 Achievements
1) Pytest 라이브러리와 테스트 코드에 대한 이해
2) Django ORM 과 ORM 최적화에 대한 이해
3) 파이썬 타입힌팅과 MyPy 라이브러리에 대한 이해
4) Bitmap 에 대한 이해

### 📌 Thoughts
Phase 1 개발 기간 동안 가장 집중했던 부분은 코드의 품질이었다. 실제 프로덕트를 만드는 것이 목적이었던 만큼
보다 실무에 가까운 기술들을 사용해보고, 실무에서 고민할 만한 사안들에 대해 고민하고자 했다.
이번 프로젝트를 진행하면서 코드 품질 측면에서 많은 공부를 했던 부분이 바로 테스트 코드와 ORM 최적화에 
대한 부분이었다.

테스트 코드를 실제 프로덕트에 적용해본 것은 이번이 처음이었는데, 
Postman 이나 Insomnia 같은 API 플랫폼을 사용하지 않고 1차적으로 내 코드를 검증할 수 있는 방법에 
대해 공부하면서 본격적으로 테스팅의 영역에 흥미를 가지게 된 것 같다. 그러면서 실제 기업에서는 어떤 테스팅
플로우를 사용하고 있을지 궁금해졌다. 하지만, 기업이나 서비스 특성, 조직에 따라 그 방법이 매우 다양하고
정형화된 방식이 있는 분야가 아니어서 그런지 생각보다 이 부분에 대한 자료는 많지 않았던 것 같다. 
테스트 엔지니어라는 직종에 종사하고 있는 사람과 커피챗을 하고 싶다는 생각이 들었다.

또, ORM 최적화에 대해 다시 공부하고 실제로 적용해보면서 ORM 최적화를 위해 고민하는 시간이 선택이 아닌
필수라는 것도 느꼈다. 기존의 코드를 리팩토링하면서 쿼리의 개수가 현저히 낮아지는 걸 경험한 후로부턴, 리팩토링할 때
한번에 뜯어 고치는 것이 아니라, 평소에 개발을 할 때 효율적인 ORM 쿼리를 작성해야겠다는 생각이 들었다. 
이 프로젝트를 시작으로 쿼리를 작성할 때 좀 더 효율성 관점에서 접근할 수 있게 되었다.

- [Django Type Hinting](https://notion.earthlyz9.dev/thoughts/django-typehinting)
- [Pytest With DRF](https://notion.earthlyz9.dev/thoughts/pytest-with-drf)
- [Django ORM 최적화 해보기](https://notion.earthlyz9.dev/thoughts/django-orm-optimization) 
