# ICAAN 프로젝트

![webstorm badge](https://img.shields.io/badge/WebStorm-000000?style=flat-square&logo=WebStorm&logoColor=white)

![react badge](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=black)
![CRA badge](https://img.shields.io/badge/Create_React_App-09D3AC?style=flat-square&logo=CreateReactApp&logoColor=black)
![nodejs badge](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=Node.js&logoColor=white)
![express badge](https://img.shields.io/badge/Express-000000?style=flat-square&logo=Express&logoColor=white)
![swagger badge](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=Swagger&logoColor=black)


![pm2 badge](https://img.shields.io/badge/PM2-2B037A?style=flat-square&logo=PM2&logoColor=white)
![mongodb badge](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=MongoDB&logoColor=white)
![aws badge](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazon-aws&logoColor=white)


![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

> **해당 프로젝트의 Repo 는 비공개입니다.**

### 💡 Summary
Play Idea 학회의 개발팀에서 활동하며 맡게 된 sw 외주 프로젝트로, 질병관리청 국립보건연구원의 주관 하에
진행되고 있는 ICAAN 연구 프로젝트의 sw 연구원으로서 백엔드 API 와 관리자 페이지 구현을 맡았다.

#### 🗓 2022.05 ~ 2022.12

#### 👥 Collaborators
본 프로젝트는 총 3명이서 함께 작업한 결과물이다. (프론트엔드 2명, 백엔드 & 프론트엔드 1명) 

나는 관리자 페이지의 프론트엔드와 백엔드 서버를 맡아 진행했다.


#### 🛠 Tech Stack
* Frontend: React
* Backend: Express.js, MongoDB (Mongoose)
* Deployment: MongoDB Atlas, PM2, EC2

#### 📋 Features
1) Mongoose 를 이용한 데이터 조작
   - 피험자 관리: 피험자 등록, 정보 수정, Bulk Add & Update, 피험자 정보 조회
   - 리소스 관리: 연구에 필요한 리소스 등록 및 수정
   - 데이터 export: xlsx 라이브러리를 이용한 데이터 파싱 및 엑셀 파일 반환 작업
   - 피험자 통계 대시보드: 피험자 관련 데이터를 시각화한 대시보드 페이지

2) 문자/예약문자 발송
   - 네이버 SENS 사용: 공지사항과 메시지를 관리자 페이지에서 전송하면 해당 유저의 전화번호로 메시지 전송
   - agenda 를 사용하여 예약 공지 및 예약 공지 문자 전송 이벤트 관리

3) 배포
   - FE: 빌드 파일을 ec2 에 직접 업로드
   - BE: GitHub Actions 를 사용하여 배포 스크립트 실행, PM2 를 이용하여 node 프로세스 관리 (fork mode)

#### 🔗 URLS
- [ICAAN 프로젝트 알아보기](http://icaan.co.kr)
- [ICAAN 프로젝트 웹앱](https://icann.net)
- [ICAAN 프로젝트 관리자 페이지](https://icaan.net/admin)

---

### 📌 Trouble Shooting
실사용 서비스의 배포가 처음이어서 발생한 미숙한 실수들이 있었다. 
그 중에서도 서비스 개발이 끝난 직후에 production 용 DB 로 변경하는 과정에서
서비스 곳곳에서 예상치 못한 에러가 발견되어 급하게 버그 픽스를 했던 적이 있는데, 
이는 기존의 더미 데이터가 모두 사라져 예외 처리를 해주지 않은 부분에서 에러가 발생한 것이었다. 
정식 배포를 위해 리팩토링을 한번 더 거쳐 꼼꼼하게 예외 처리를 해주었다.
이를 계기로, 사전 설계를 할 때와 실제로 개발을 할 때 모두 예외 처리 경우에 대해 체계적으로 고민하고 꼼꼼하게 확인해야함을 몸소 배울 수 있었다.

### 📌 Achievements
1) Express.js 프레임워크에 대한 이해, 프로젝트 구조에 대한 고민
2) PM2 에 대한 이해
3) MongoDB 에 대한 이해와 활용
4) GitHub Actions 활용 방법

### 📌 Thoughts
Express 나 React 모두 처음 다뤄보는 것들이라 공부할 것이 굉장히 많았다. 개발 기간이 넉넉한 편이라 공부와 병행할 수 있었던 점이
다행이었다. 학회 개발팀에서 백엔드 개발을 맡고 있지만 프론트엔드 개발까지 맡게 되면서 React 공부도 하게 되었는데, 처음에는 워크로드가 커서 걱정이었지만
오히려 프론트에서 내가 설계한 api 를 직접 써보면서 백엔드 api 설계에 대해 고민하고 수정할 수 있는 기회가 되었다.


개발 사전 미팅부터 서비스 설계, 서비스 구현까지 포괄적인 과정에 모두 참여하면서 개발 측면 뿐만 아니라 보다 거시적인 관점에서
하나의 서비스를 개발하고 보수하는 과정에 대한 전반적인 이해도 역시 높일 수 있었다. 또한 프레임워크에 대한 이해뿐만 아니라
지속적으로 작동해야하는 서비스를 개발하는 것인 만큼 배포한 서비스의 안정성이나 서버의 성능, 네트워크 응답 속도 등 여러가지 요소들에
대해 고민하고 공부할 수 있는 기회였다.


개발 측면에서도 배운 점이 정말 많지만 무엇보다 내가 개발한 서비스에 대한 책임감을 갖게 해주었다는 점에서
의미가 크다. 무에서 유를 창조하고 그 서비스가 실제로 중요한 곳에 사용된다는 점에서 재미있고 보람찼지만 
6개월이라는 시간동안 꾸준히 서비스를 개발하고 발전시키기 위한 고민을 했던 과정을 돌아보니
내가 만든 서비스에 대한 애정과 책임감이라는 감정이 더 크게 다가오는 것 같다. 


