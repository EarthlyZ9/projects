# Space Gem


![vs badge](https://img.shields.io/badge/VisualStudio-5C2D91?style=flat-square&logo=VisualStudio)
![csharp badge](https://img.shields.io/badge/C_Sharp-239120?style=flat-square&logo=CSharp&logoColor=white)
![unity badge](https://img.shields.io/badge/Unity-ffffff?style=flat-square&logo=Unity&logoColor=black)

![logo](https://user-images.githubusercontent.com/89679621/208043866-09ea8336-d5bd-47b8-b653-e8bfadff7237.jpeg)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

[깃헙 레포 바로가기](https://github.com/EarthlyZ9/SpaceGem.git)



### 💡 Summary
게임 엔진 Unity 와 C# Script 를 사용한 레트로 느낌의 캐주얼 액션 게임 제작!


### 👀 Space Gem 소개
* __게임 이름:__ Space Gem
* __게임 장르:__ 캐주얼 액션
* __목표:__ 미끄러지는 구를 방향키와 스페이스바로 조작하여 스테이지의 모든 보석을 획득한 뒤, 결승 포탈까지 도달한다.
* __설명:__ 총 3개의 스테이지로 이루어져 있으며, 보석을 모두 획득하지 않고 포탈에 도달하거나 맵에서 떨어지면 처음부터 다시 시도해야 하며, 보석을 모두 획득하여 포탈에 도달하면 자동으로 다음 스테이지로 넘어간다.

#### 💎 구성요소


* __공 (Player):__ 사용자가 조작할 sphere object. 방향키와 스페이스바 (점프) 를 사용하여 조작하게 되며 공의 특성상 힘을 가하면 미끄러지는 듯한 느낌이 있다.
* __아이템 (Item):__ 엔드포인트까지 가는 길에 획득해야 하는 아이템. 모든 아이템을 다 획득해야 게임이 완료된다. 다 획득하지 못하면 자동으로 재시도 한다.
* __지형 (Platform):__ 플레이어가 움직이게 될 맵.
* __결승점 (Endpoint):__ 지형 끝에 위치해 있는 포탈. 모든 아이템을 획득한 후 통과하여야 한다.


#### 💎 Scene 구성


* __Start:__ 보석 이미지를 누르면 player 선택화면으로 넘어간다.

* __Player Selection:__ player 공의 색깔을 고를 수 있다. 원하는 플레이어 색을 클릭하면 stage 1으로 넘어간다.

* __Stage_1:__ 첫번째 스테이지

* __Stage_2:__ 두번째 스테이지

* __Stage_3:__ 세번째 스테이지

* __Complete:__ 모든 스테이지를 완료하면 볼 수 있는 페이지 (다시 Start 로 갈 수 있는 버튼 존재)



#### 🗓 2022.10

### 📋 Features
* 유저 선택 (다양한 Material 적용)
* Player 모델의 이동 (방향키와 스페이스바)
* Universal Renderer Pipeline Shader Graph 를 기반으로 한 Material 생성
* Scene 전환
* Game Manager 을 통한 Scene 및 게임 정보 관리
* 다양한 Audio Source 적용

### 🛠 Tech Stack
* Unity, C Sharp
* Windows Build, WebGL Build


### 📌 Takeaways
이 프로젝트를 진행하면서 얻을 수 있었던 가장 큰 교훈은 '테스트를 고려한 어플리케이션의 설계가 중요하다' 라는 점이다.
Unity 로 작업을 하는 것이 Scene 이나 Script 에 변동 사항을 적용하고 Game simulation 을 실행시키는 데에 상당한 시간이 걸려,
테스트를 하는 데에 많은 시간이 소요되고 빠르게 에러를 찾아내고 디버깅하는 것이 어려웠다. 작은 웹 프로젝트의 경우에는
설계와 디버깅에 엄청난 체계가 없어도 개발 과정에서 큰 어려움을 느끼지 못했으나 프로젝트가 커지고 로직이 복잡해질수록 
테스트 자체도 하나의 병목으로 작용할 수 있겠다는 생각이 들었다. 본격적으로 개발에 들어가기 전에 어플리케이션의 특성을 반영한
테스트 단계를 고려하여 설계하고 체계적이고 효율적으로 디버깅할 수 있는 방법을 고안해내야함을 느꼈다. 

이 과정에서 Test Driven Development (TDD) 의 효용성에 대해서도 생각해보게 되었다. 
테스트의 무결성을 보장할 수 없다는 점, 테스트 코드를 짜는데 많은 자원을 활용하게 되면서 주객전도가 될 수 있다는 점 등 
단점이 존재하고 모든 것의 해답이 될 수 없는 방식이긴 하지만 설계 단계에서부터 프로그래밍 목적이 굉장히 분명하고 
의도하는 input 과 output 케이스가 명확한 경우 상당한 효용성이 있을 것 같다는 생각이 들었고 도입해볼만 하다는
생각이 들었다.

