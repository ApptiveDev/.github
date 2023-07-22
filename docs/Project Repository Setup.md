- [Overview](#overview)
- [Repository Naming](#repository-naming)
- [Branch Protection](#branch-protection)
- [Squash Merge](#squash-merge)
- [Branch Auto Deletion](#branch-auto-deletion)
- [Code Review Approval](#code-review-approval)


## Overview
 이 문서에서는 [동아리 협업 가이드라인]()을 위한 리포지토리 세팅을 설명합니다. 

## Repository Naming
![Repository Naming](https://i.imgur.com/7XCN1Vc.png)  
 리포지토리는 프로젝트명 및 `apptive`, 기수, 포지션을 표시해야 합니다.
 - 리포지토리 이름은 `프로젝트명-포지션`으로 한다.
    - 프로젝트명의 대소문자 구분은 자유
    - 포지션은 소문자로만 구성 (backend/frontend/android)
    - ex) PNU-backend, PNU-android, PNU-frontend 
 - `apptive`와 기수는 리포지토리 태그(topic)에 넣는다.

## Branch Protection
![Branch Protection](https://i.imgur.com/u4a5cht.png)  
[Settings] > [Branches] > [Add rule]에서 `main` 브랜치에 대해 다음 두 가지를 설정합니다.
- [x] Require a pull request before merging
- [x] Require conversation resolution before merging

이제 main 브랜치에는 직접 커밋이 불가능하며, 코드리뷰를 모두 마친 Pull Request만으로 가능합니다.

## Squash Merge
![Squash Merge](https://i.imgur.com/0Pl4fhv.png)  
[Settings] > [General] > [Pull Requests]에서 `Allow squash merging`만 활성화하고, `Default to pull request title`을 선택합니다. 앞으로 PR의 커밋들은 하나로 합쳐져서 병합되며 추가되는 커밋 명은 PR명이 됩니다. 

## Branch Auto Deletion
![Branch Auto Deletion](https://i.imgur.com/RZu7Ppn.png)  
[Settings] > [General] > [Pull Requests]에서 `Automatically delete head branches` 항목을 체크합니다. PR 병합 이후 해당 원격 브랜치는 자동으로 삭제됩니다.