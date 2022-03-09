# CONTRIBUTING.md
Issue 화면            |  Pull Request 화면
:--------------------:|:------------------:
![표시 위치](https://user-images.githubusercontent.com/51331195/156929682-66c7647c-666f-4652-bbae-3ef0f91ca9a8.png) | ![표시 위치](https://user-images.githubusercontent.com/51331195/156929788-9000a4a0-e102-4034-8dd2-d1ee9c8df373.png)


 이 문서에서는 동아리에서 권장하는 컨벤션 및 협업 가이드라인을 설명합니다.  
 이 페이지에 대한 링크는 위와 같이 PR, Issue 화면에 자동으로 표시됩니다.
 
## 목차
- [CONTRIBUTING.md](#contributingmd)
  - [목차](#목차)
  - [브랜치 관리 전략](#브랜치-관리-전략)
    - [Github Flow](#github-flow)
    - [Pull Request](#pull-request)
    - [Commit](#commit)
  - [코드 리뷰](#코드-리뷰)
  - [코딩 컨벤션](#코딩-컨벤션)
  - [버전과 릴리즈](#버전과-릴리즈)

## 브랜치 관리 전략
![image](https://user-images.githubusercontent.com/51331195/156977445-fad7d1bf-eac8-4fbd-aea5-4d6b80beef21.png)  
 브랜치 관리 전략은 간단하게 Github Flow를 따르고자 합니다.  
 앱을 출시하게 되면 Git Flow로 전환할 수 있습니다.
 
### Github Flow
- **master**와 브랜치로 구성된다.
- **master**는 항상 배포가 가능한 안정된 상태여야 한다.
- 개발 작업은 항상 브랜치에서 이루어져야 한다.
- 버그 해결, 기능 개발 단위로 브랜치를 딴다.
- 브랜치 명은 현재 하고 있는 작업을 나타낸다.

### Pull Request
- PR 이전에 1차적으로 구동 테스트를 한다.
- PR은 버그 해결, 기능 조각 구현 등 작은 단위가 좋다.
- 무거운 기능 구현은 중간중간 PR을 올린다.
- PR 제목은 처리한 작업을 알 수 있도록 적는다.

### Commit
 : 동아리 커밋 컨벤션은 [Commit Convention](https://github.com/Apptive2022-1/.github/blob/main/docs/Commit%20Convention.md)를 참고해주세요. 아래는 그중에서 중요한 항목들입니다.
 * 커밋은 시간 순서대로 쌓는다.
 * 커밋 제목은 히스토리로부터 변경 내역을 쉽게 알 수 있도록 적는다.
 * 서로 밀접한 연관 또는 종속성을 갖는 변경내역은 하나의 커밋으로 합친다.
 * 커밋 제목에는 반드시 접두사를 붙인다.

## 코드 리뷰

## 코딩 컨벤션

## 버전과 릴리즈


