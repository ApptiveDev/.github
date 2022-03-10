# 패키지 컨벤션
|클린 아키텍처            |  아키텍처 상세 |
|:--------------------:|:------------------:|
|![클린 아키텍처](https://user-images.githubusercontent.com/51331195/157505761-e79cc80a-1301-4492-8441-dd3d7f21234b.png) | ![Flow](https://user-images.githubusercontent.com/51331195/157505816-10b27794-9bb6-4676-a186-3bee81683060.png) |

## 레이어 패턴
 Martin Fowler가 제시한 Presentation-Domain-Data 레이어 구분을 따르고자 합니다. 이 구조는 UI 요소가 존재하는 다양한 소프트웨어에 적용할 수 있는 기본적인 구조입니다. 관심사를 세 가지 큰 영역으로 구분함으로써 클래스나 로직의 위치를 쉽게 식별할 수 있고, 개발할 때에는 한 영역에만 집중할 수 있게 됩니다.

 ### Presentation
  : UI와 관계된 요소를 모두 담습니다. View, ViewModel, Navigation 모듈 등이 여기에 속합니다.

 ### Domain
  : UI와 데이터 영역 이외의 모든 코드가 여기에 담깁니다. 순수 언어(코틀린 등)으로 짜인 컨트롤러 등이 여기에 속합니다.

 ### Data
  : Persistence(영속성)과 연관이 깊은 요소를 담습니다. DB, Network, DTO 등이 여기에 속합니다.

## 프로젝트 구조
```
|-app
    |- _constants
    |- _enums
    |- data
        |- mapper
        |- room
            |- dao
            |- entity
        |- network
            |- dto
            |- api
        |- storage
    |- domain
        |- interfaces
        |- mapper
        |- model
        |- repository
        |- utils
    |- presentation
        |- mapper
        |- model
        |- component
        |- view
            |- <화면1>
            |- <화면2>
            |- ...
        |- viewmodel
        |- navigation
```

## :link: 참고
* [Presentation-Domain-Data Layering](https://martinfowler.com/bliki/PresentationDomainDataLayering.html)
