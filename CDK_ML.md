# AWS CDK Lambda Function


![python badge](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white)
![aws badge](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazon-aws&logoColor=white)

![github](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white)

> **해당 프로젝트의 Repo 는 비공개입니다.**



### 💡 Summary
데이터팀이 만들어준 XGBoost 추론 모델을 AWS Lambda Function 을 사용하여 endpoint 로 접근할 수 있게 한다.
토큰과 데이터를 endpoint 로 보내면 모델을 돌려 추론 결과를 response 로 반환한다.


#### 🗓 2023.02

### 📋 Features
* XGBoost 추론 모델의 결과값 반환


### 🛠 Tech Stack
* AWS Lambda
* AWS CDK for Python


### 📌 Takeaways
완성된 모델을 전달받아 배포만 하면 되는 작업이라 그 자체론 복잡할 건 없었지만 AWS CDK 을 이용해서 
AWS 리소스를 관리하는 건 처음해보는 것이라 초기 세팅을 위해 공부를 꽤 해야했다. 
AWS를 자주 사용하긴 하지만 항상 콘솔로 조작해왔어서 IDE 안에서 소스코드 뿐만 아니라 
인프라도 관리할 수 있다는게 굉장히 생소했고 처음에는 콘솔을 사용하는 것보다 불편할 것 같다는 생각도 들었다. 
처음에는 CDK 가 너무 답답해서 IDE 에서도 deploy를 했다가 코드 변경 없이 콘솔에서 또 다른 수정 사항을 반영해서 
리소스 스택이 완전히 꼬여 다시 처음부터 시작하기도 했다...
하지만 공부하다보니 처음의 생각과는 다르게 러닝 커브가 조금 높아도 오히려 CDK 가 관리에 용이할 것 같다는 생각이 들었다. 
보통 형상 관리라고 하면 소스코드의 관리 정도일텐데 CDK 를 사용하면 리소스 변동 사항에 대해서도 
버전 관리를 할 수 있다는 것이 큰 메리트인 것 같다. 버전관리와 더불어 워크플로우만 잘 수립하면 
여럿이서 하나의 리소스를 효율적으로 조작하는 것도 가능하겠다는 생각이 들었다. 
이런 간단한 배포 작업을 할 때에도 CDK 의 강점을 느낄 수 있었다면 여러 리소스를 사용하는 프로젝트인 경우 그 효용이 더 크게 다가오지 않을까하는 생각이 든다.


