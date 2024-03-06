# Step In

![intellij badge](https://img.shields.io/badge/IntelliJ-000000?style=flat-square&logo=IntelliJ-IDEA&logoColor=white)

![springboot badge](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=SpringBoot&logoColor=white)
![springsecurity badge](https://img.shields.io/badge/SpringSecurity-6DB33F?style=flat-square&logo=SpringSecurity&logoColor=white)
![jwt badge](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=JSONWebTokens&logoColor=white)
![mysql badge](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white)

![tomcat badge](https://img.shields.io/badge/Tomcat-F8DC75?style=flat-square&logo=ApacheTomcat&logoColor=black)
![docker badge](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

[깃헙 레포 바로가기](https://github.com/EarthlyZ9/Step-In)



### 💡 Summary
개인적으로 API 설계할 때 Top-Down 의 사고 흐름을 선호하는 편인데 Fan out 형식 (계단식) 으로 아이디에이션하고
이를 기록하기에 적합한 툴이 없다고 느꼈다. (내가 찾지 못한 것일 수도 있지만...) DBDiagram 과 같은 툴처럼 자유롭게
내 생각의 흐름을 기록하고 분기하며 아이템을 생성하고 메모를 작성할 수 있는 툴이 있으면 좋을 것 같다는 생각에 기획하게 되었다.
기본적으로 프로젝트를 생성하여 해당 프로젝트의 워크스페이스에서 칼럼에 해당하는 여러 Step 들을 생성하고 Step 하위에 여러개의 Item을 생성하며,
이전 Step 의 Item 을 부모 Item 으로 갖는 형태를 취한다. 이런 방식을 통해 큰 Step 에서 시작하여 작은 Step 으로 구체화 및 분기 해나가면서
Top-Down 흐름의 사고를 기록할 수 있을 것이라고 생각했다. 현재 JWT 인증 플로우, OAuth2 가 구현된 API 는 존재하나 프론트엔드 개발자를
찾지 못해 웹페이지 개발은 하지 못한 상태이다.

#### 🗓 2023.05

#### 👥 Collaborators
본 프로젝트는 총 2명이서 함께 작업할 결과물이었다. 슬프게도 프론트엔드 개발자를 구하지 못했다.


#### 📋 Features
1) Full authentication flow
   -  커스텀 UsernamePasswordAuthenticationFilter 을 통한 json 로그인
   - 커스텀 JwtAuthenticationFilter 를 통한 jwt 인증 플로우(http-only secure cookie refresh token 이용)
   - spring-boot-oauth2-client dependency 의 내부 코드를 참고하여 네이버/카카오/구글 OAuth2 로그인 구현

2) 프로젝트 생성/수정/삭제
   - DB 설계: 프로젝트 하위에 Step 을 생성 - 그 하위에 Item 을 생성 - 이전 Step 의 Item 을 부모 Item 으로 지정
   - Flyway 를 사용한 migration 관리

#### 🛠 Tech Stack
- Backend: SpringBoot, SpringSecurity, OAuth2, MySQL, Flyway, Tomcat, Docker

---

### 📌 Trouble Shooting
API 만 개발하는 것이었기에, Spring security configuration 클래스의 ```oauth2Login()``` 을 사용할 수 없어
자체 oauth2 서비스를 구현하기 위해 spring-security-oauth2-client 종속성의 내부 코드를 참고하였다. 
이를 통해 OAuth2 프로토콜을 코드로서 이해하고, rest client 를 사용하여 직접 인증 요청을 보내는 코드를 작성할 수 있었다.

### 📌 Achievements
1) Spring Framework 동작 원리 이해
2) Spring Security 의 Filter Chain 원리 이해
3) OAuth2 프로토콜 이해
   > Spring Security 를 사용한 인증 플로우 구축에 대한 자세한 내용은 이 [링크](https://notion.earthlyz9.dev/thoughts/spring-security/jwt-filter)의 포스팅 시리즈 참고
   
### 📌 Thoughts
이번 프로젝트를 통해 Spring Framework 를 처음 접해보았다. 개인적으로 이 프로젝트의 목표는 'Spring Framework 와 친해지기' 
그리고 'Spring Security 를 통해 나만의 인증 플로우 구축하기' 였다. Spring 이라는 프레임워크에 첫발을 딛은 도전이었는데
정말 말로만 듣던 것처럼 생태계가 방대함을 느꼈다. 그래서 이 프로젝트의 목표를 Spring Framework 의 기본동작과 
Spring Security 원리를 이해하는 것으로 좁혔다. 개발 측면에서는 jwt 인증 플로우와 oauth2 인증 플로우 구축에 도전해보았는데
이를 통해 Spring Security 의 Filter chain 과 OAuth2 인증 과정에 대해 공부할 수 있었다. 

Spring 을 사용하면서 느꼈던 다른 프레임워크와의 차이점은 스프링이 유독 '매우 많은 규칙들의 집합으로서의 프레임워크' 의 느낌이 강하다는
점이었다. 물론 스프링이 개발자들에게 상당한 자유도와 유연성을 주는 프레임워크로 알려져있지만 뉴비의 입장에서는 지켜야할 컨벤션이나 규칙이 많아
시작 단계에서는 자유도의 제한을 받는다고 느꼈던 것 같다. 특히 혼자 작업하는 입장에서 이렇게까지 해야하나 라는 생각이 드는 부분들도 많있지만
기업 입장에서는 규칙과 컨벤션이 지켜주는 환경에서 확장성 있게 개발하기 좋은 환경일 것 같다는 생각이 들었다. 확실히 혼자 공부하다보면
프레임워크가 가진 장점을 백프로 느낄 수 없는 것 같다. 실제 기업 수준에서는 어떤 식으로 프로젝트 구조가 관리되는지 매우 궁금하다!


