# CONTRIBUTING.md
Issue 화면            |  Pull Request 화면
:--------------------:|:------------------:
![표시 위치](https://user-images.githubusercontent.com/51331195/156929682-66c7647c-666f-4652-bbae-3ef0f91ca9a8.png) | ![표시 위치](https://user-images.githubusercontent.com/51331195/156929788-9000a4a0-e102-4034-8dd2-d1ee9c8df373.png)


 이 문서에서는 동아리에서 권장하는 컨벤션 및 협업 가이드라인을 설명합니다.  
 이 페이지에 대한 링크는 위와 같이 PR, Issue 화면에 자동으로 표시됩니다.
 
## 📌 목차
- [📌 목차](#-목차)
- [🔱 브랜치 관리 전략](#-브랜치-관리-전략)
  - [Branch](#branch-github-flow)
  - [Pull Request](#pull-request)
  - [Commit](#commit)
- [✔️ 코드 리뷰](#️-코드-리뷰)
- [📂 패키지 컨벤션](#-패키지-컨벤션)
- [💅 코딩 컨벤션](#-코딩-컨벤션)
- [🧱️ 버전과 릴리즈](#️-버전과-릴리즈)

## 🔱 브랜치 관리 전략
Github Flow            |  Squash Merge
:--------------------:|:------------------:
![image](https://user-images.githubusercontent.com/51331195/156977445-fad7d1bf-eac8-4fbd-aea5-4d6b80beef21.png) | ![im-developer.tistory.com/182](https://github.com/ApptiveDev/.github/assets/51331195/6191feb8-fedc-45b6-bbc4-7521400929f8)
  
 동아리의 브랜치 관리 전략은 간단하게 Github Flow에 더해 Squash Merge를 기본으로 합니다.  
 브랜치 관리 전략을 위한 리포지토리 세팅은 [별도 문서](https://github.com/ApptiveDev/.github/blob/main/docs/Project%20Repository%20Setup.md)를 참고해주세요.
  > 브랜치 관리 전략에는 Github Flow, Git Flow, Gitlab Flow 등이 있습니다. 작은 규모일 경우 Git Flow는 필요 이상으로 복잡하게 하므로 초기 협업에는 Github Flow가 적당합니다. 서비스 구실을 갖추고, 팀의 규모가 늘어날 때쯤 다른 전략으로 변경하길 권장합니다.

 > Squash Merge는 브랜치가 병합될 때 커밋들이 PR 제목으로 합쳐지게 됩니다. 커밋은 개인마다 기준이 조금씩 다른 반면, PR/브랜치는 이슈 단위로 생성하므로 일관된 기준으로 커밋을 쌓을 수 있어 히스토리 추적을 용이하게 합니다.

 
### Branch (Github Flow)
- **master**와 개인 브랜치로 구성된다.
- **master**는 항상 배포가 가능한 안정된 상태여야 한다.
- 브랜치 명은 본인 이름, 이슈번호, 작업 내용을 포함한다.
    - ex) `wonseok/#3/add-account-setting-tab`
- 개발 작업은 항상 브랜치에서 이루어져야 한다.
- 버그 해결, 기능 개발 등 이슈/티켓 단위로 브랜치를 딴다.

### Commit
: 커밋은 PR 내용을 작성할 때 도움을 주는 역할을 합니다. 자세한 커밋 작성 기준은 [Commit Convention](https://github.com/Apptive2022-1/.github/blob/main/docs/Commit%20Convention.md)을 참고해주세요.
 * 커밋은 시간 순서대로 쌓는다.
 * 커밋 제목은 변경 내역을 쉽게 알 수 있도록 적는다.
 * 서로 밀접한 연관 또는 종속성을 갖는 변경내역은 하나의 커밋으로 합친다.

### Pull Request
- PR 이전에 타겟 브랜치에 대해 `rebase`를 진행한다.
- PR 제목은 `[<이슈번호/티켓번호>] 작업한 내용` 형식을 따른다.
    - ex) `[#3] 인트로 화면에 계정관리 탭 추가`
    - 이슈/티켓이 없을 경우 `[NOISSUE]`를 붙인다.
- PR은 버그 해결, 기능 조각 구현 등 작은 단위가 좋다.
- PR 이후 원격 브랜치는 삭제한다.
  
## ✔️ 코드 리뷰
 : 자세한 내용은 [별도 문서](https://github.com/Apptive2022-1/.github/blob/main/docs/Code%20Review.md)를 참고해주세요
 1.  **코드 작성자**는 변경내역을 요약하여 PR을 올립니다.
      * 변경내역이 너무 많지 않도록 분량 조절
      * 관련된 이슈는 #(이슈번호) 붙이기
 2.  **리뷰어**는 코드를 천천히 읽어봅니다.
      * 문제가 없으면 'Approve' 표식 달기
      * 의견, 우려되는 부분 등은 'Comment' 또는 'Request Changes' 표식 달기
 3. **코드 작성자**는 리뷰를 읽고 수정 후 Merge합니다.
      * 하루 이상 리뷰가 진행되지 않는다면 임의로 Merge 가능
   
## 📂 패키지 컨벤션
 패키지 컨벤션(프로젝트 구조)는 기본적으로 다음을 따릅니다. 이는 [Clean Architecture](https://developer.android.com/jetpack/guide)와 [Presentation-Domain-Data](https://martinfowler.com/bliki/PresentationDomainDataLayering.html) 레이어를 기초로 합니다. 자세한 내용은 [별도 문서](https://github.com/Apptive2022-1/.github/blob/main/docs/Package%20Convention.md)를 참고해주세요.
 ```m
|-app
    |- _constants         // Color, Size 등 UI 요소
    |- _enums             
    |- data
        |- room
            |- dao
            |- entity
        |- network
            |- dto
            |- api        // SharedPreference, Datastore 등
        |- storage
    |- domain
        |- interfaces
        |- mapper         // data <-> domain 맵퍼
        |- model
        |- repository
        |- utils          // 컨트롤러 등
    |- presentation
        |- mapper         // domain <-> presentation 맵퍼
        |- model
        |- component      // 공통으로 사용할 UI 컴포넌트 (공유 컴포저블 등)
        |- view
            |- <화면1>
            |- <화면2>
            |- ...
        |- viewmodel
        |- navigation
``` 

## 💅 코딩 컨벤션
 코드 스타일을 맞추면 가독성이 좋아져 코드리뷰하기 편해집니다. 네이밍 룰(파스칼, 스네이크 등)부터 클래스 멤버 순서, 중괄호 생략 여부, 가로/세로 공백 등 영역이 다양하여, 페어 프로그래밍이나 코드 리뷰를 통해 천천히 맞추어 나가기를 추천합니다. 컨벤션 문서는 다음을 참고해주세요.
  - **한글**: [코틀린 스타일 가이드 - 구글](https://developer.android.com/kotlin/style-guide?hl=ko)
  - **영어**: [Kotlin Coding Convention](https://kotlinlang.org/docs/coding-conventions.html)
  
## 🧱️ 버전과 릴리즈
| Semantic Versioning |
|:-------------------:|
|![SemVer)](https://user-images.githubusercontent.com/51331195/157697539-25121f51-91ea-4afb-af9e-3e8133c7ebe8.png) |

Versioning은 팀원과 소통하고 협업하기 위한 수단입니다. 산출물로 **릴리즈 노트**를 작성하게 되고, 기획자와 디자이너 등 테스터는 이슈와 피드백을 전달합니다. 다음 버전은 이 이슈와 피드백을 반영해야 합니다.

**버전**
- 테스팅이 가능한 시점부터 0.1.0이다.
- 페이지 및 기능 단위로 쪼개 개발한다.
- 이슈와 피드백은 Github 이슈에 등록하여 관리한다.
- 릴리즈 노트는 협업툴 (Notion 등)이나 Github 레포지토리를 활용한다.
-  회의 → 피드백 → 개발 → 버전업 → 회의 사이클을 되도록 준수한다.
  
**릴리즈**
- Github Repository의 자동완성 기능을 활용한다.
- 변경사항, 버그수정 등 사용자의 관점에서 작성한다.
- 리팩토링 내역 등은 포함할 필요 없다.
