# 리눅스 개발환경 설정
- [Overview](#overview)
  - [Why Linux/Mac](#why-linuxmac)
  - [Prerequisites](#prerequisites)
- [Installation](#installation)
- [System Setting](#system-setting)
  - [한글 키보드](#한글-키보드)
- [Shell Setting](#shell-setting)
  - [Zsh](#zsh)
  - [Terminator](#terminator)
- [Tools](#tools)
  - [Vim](#vim)
  - [Git](#git)
  - [Docker](#docker)
- [Program](#program)
  - [VS Code](#vscode)
  - [pinta (그림판)](#pinta-그림판)
  - [obs-studio (화면 녹화)](#obs-studio-화면-녹화)


## Overview
 이 문서에서는 동아리 프로젝트 개발에 유용한 우분투(리눅스) 설정 및 플러그인, 프로그램 등을 소개합니다. 동아리 개발문서는 리눅스를 기준으로 작성될 것이므로 윈도우를 이용하고 있다면 이 문서에 따라 개발환경을 설정하기를 권장합니다. 백엔드 개발자라면 반드시 리눅스나 MacOS 환경에서 개발하시기 바랍니다.

### Why Linux/Mac
 윈도우 프로그램은 대부분 GUI 개발을 수반하고 커맨드라인도 UNIX 명령어와 많은 차이가 있습니다. 또한 윈도우의 라이센스로 인해 공개되지 않은 소스코드가 많으며 소프트웨어 개발 중 OS 레벨의 문제를 발견하면, 마이크로소프트 측에 개선 요청을 해야만 피드백을 받을 수 있습니다. 리눅스로 개발하는 주된 이유는 이처럼 **커맨드라인 환경**과 **오픈소스** 두 가지이며 이미 비즈니스 레벨의 수많은 개발툴은 리눅스(UNIX)를 기반으로 합니다. MacOS는 UNIX를 기반으로 하고 있고, 커맨드라인 환경을 지향하므로 MacOS도 개발에 좋은 옵션입니다. 

 - 다양한 개발툴은 리눅스를 바탕으로 한다. (Docker, Kubernetes, Bazel 등)
 - AWS, GCP 등 배포 환경 및 원격접속 환경은 리눅스이다. (ssh)
 - CI/CD는 리눅스 명령어로 작성된다.
 - 자동화 스크립트를 작성하려면 커맨드라인 환경에 익숙해야 한다.

### Prerequisites
  - 16GB+ USB
  - [Ubuntu 22.04/23.04 이미지](https://ubuntu.com/download/desktop)
  - 리눅스에 할당 가능한 100GB+의 여유공간 
## Installation
 동아리는 Ubuntu 22.04LTS 또는 23.04를 기준으로 합니다. 설치는 다음 블로그 글을 참고하시기 바랍니다.
1. 부팅 USB 만들기: [블로그 글](https://heisanbug.tistory.com/17)
2. 우분투 설치: [블로그 글](https://jimnong.tistory.com/676)

 우분투 설치 시 파티션 축소를 건너뛰고 `Windows를 그대로 두고 설치` 옵션을 선택해도 됩니다. 그러면 파티션 설정을 우분투 설치 중에 하게 됩니다. (노트북이나 BIOS 설정에 따라 안 되는 경우도 있음)

## System Setting
### 한글 키보드
🔗 [Ubuntu 키보드 한글 입력 설정 하기](https://shanepark.tistory.com/231)  

## Shell Setting

### Zsh
&nbsp;zsh은 리눅스 기본 bash 보다 다양한 확장 기능을 제공하는 터미널 쉘입니다. 터미널 테마와 자동완성, 텍스트 하이라이트 등 유용한 플러그인 덕분에 개발에 필수적이라 할 수 있습니다. Zsh은 Mac OS의 기본 터미널 쉘이기도 합니다.  
**설치방법**: 🔗 [Install and Setup ZSH on Ubuntu Linux](https://itsfoss.com/zsh-ubuntu/#install-zsh-on-ubuntu)
```bash
# zsh 설치 및 첫 환경설정
$ sudo apt install zsh git fonts-font-awesome
$ zsh          // 주로 0번이나 1번 선택
$ which zsh    // 설치여부 확인

# zsh을 기본 쉘로 설정 (-s = 특정 쉘로 설정)
# 설정 이후 재로그인 또는 재부팅 필요
$ chsh -s $(which zsh)
```
#### Oh My Zsh
&nbsp;OMZ는 Zsh에 다양한 부가 기능을 추가 및 관리해주는 플러그인입니다. 대표적으로 자동완성, 간편한 명령어 별명 기능 등이 있습니다. 아래 커맨드라인을 통해 설치가 완료되면 ```.zshrc```가 업데이트되며, 자동으로 OMZ가 반영됩니다.  
**설치방법**: 🔗 [Oh My Zsh Installation](https://github.com/ohmyzsh/ohmyzsh/tree/master#basic-installation)
```bash
// OMZ 설치용 쉘 스크립트 다운로드 및 실행
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```

#### 플러그인 (Auto Suggestion, Syntax Highlight, ...)
![image](https://github.com/ApptiveDev/.github/assets/51331195/98b9c881-5707-4f52-b1e1-6a15eade34b1)
- [Auto Suggestion](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh): 최근 사용한 명령어를 자동으로 추천해주는 기능
- [Syntax Highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh) : 문자열, 유저명 등 텍스트에 색상을 입히는 기능. 잘못된 명령어는 빨간색으로 표시됨.
- History Search: 현재 프롬프트에 입력된 텍스트에서 화살표 키를 통해 최근 사용된 명령어를 검색
```bash
# 기본 플러그인 폴더에 Auto Suggestion, Syntax Highlight 소스코드 다운로드
$ git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh 환경설정
$ vi ~/.zshrc

# .zshrc 내에서 플러그인 활성화
plugins=( 
    # other plugins...
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
)

# .zshrc 내에서 명령어 히스토리 단축기 설정 (적당한 곳에 아래 2줄 복붙)
bindkey "^[[A" history-beginning-search-backward    # ↑ (이전 명령어)
bindkey "^[[B" history-beginning-search-forward     # ↓ (최근 명령어)

# zsh 새로고침
$ source ~/.zshrc
```

### Terminator
![image](https://github.com/ApptiveDev/.github/assets/51331195/c57fd26b-fbef-4f88-a159-f93d2f466822)  
Terminator는 한 터미널 창에서 여러 터미널을 분할해 사용할 수 있도록 하는 프로그램입니다. 더 확장된 프로그램으로 `tmux`를 사용할 수 있습니다.
```bash
# Terminator 설치 및 기본 터미널로 설정 (Ctrl + Alt + T)
$ sudo apt install terminator
$ sudo update-alternatives --config x-terminal-emulator
```

## Tools

### Vim
 vim은 텍스트 에디터로, 각종 config 파일이나 YAML, XML 등의 파일을 편집할 때 자주 사용하고, 특히 git 커밋 메시지 등을 편집할 때 유용합니다.
```bash
$ sudo apt-get update
$ sudo apt-get install vim 
```

### Git
```bash
# git 설치
$ sudo apt-get update
$ sudo apt-get install git

# git 기본 텍스트 에디터로 vim 설정
$ git config --global core.editor "vim"
```

### Docker
🔗 [Official Installation](https://docs.docker.com/engine/install/ubuntu/)  
흔히 말하는 컨테이너 플랫폼인 Docker는 **Docker Engine**을 뜻합니다. Docker는 가상화를 위해 Linux의 내장 Virtual Machine 기능을 요구하며, **Docker Desktop**은 Linux가 아닌 다른 운영체제(Windows, Mac)에서 이를 지원하기 위한 GUI 도구입니다. 따라서 리눅스는 Docker Engine을 설치하고, 다른 운영체제는 Docker Desktop을 설치해야 합니다. 위에서 apt repository 등록 및 Docker Engine 설치 절차를 따르시기 바랍니다.

## Program
### VSCode
**(설치방법)**
먼저 [VS Code](https://code.visualstudio.com/download)에서 .deb 파일을 다운로드한 후 다음 명령어를 실행합니다.
```
$ sudo apt install ~/Downloads/<파일명>.deb
$ code --version
```

**추천 확장프로그램**
- **GitLens**: 에디터에서 어떤 부분이 어떤 커밋에 의해 수정되었는지 알 수 있음
- **GitGraph**: 커밋, 브랜치 히스토리를 시각적으로 표현
- **Markdown All In One**: 마크다운 문서(.md) 편집 시 미리보기 가능
- **Markdown Emoji**: 마크다운 미리보기에서 이모티콘까지 렌더링 (단, 이모티콘 텍스트는 [여기](https://gist.github.com/rxaviers/7360908)서 확인)

### pinta (그림판)
![image](https://github.com/ApptiveDev/.github/assets/51331195/06d7dc22-7b28-4690-b7a8-19cd556a74c4)  
**(설치방법)**  
[Ubuntu Software] -> Pinta 검색 및 설치


### obs-studio (화면 녹화)
![image](https://github.com/ApptiveDev/.github/assets/51331195/75c23bdb-9a0e-4e8e-a2e7-7e674304555c)  
**(설치방법)** 🔗 [OBS Linux Installation](https://obsproject.com/kb/linux-installation)  
```bash
// apt 리포지토리 등록 및 설치
sudo add-apt-repository ppa:obsproject/obs-studio
sudo apt install obs-studio

// 실행
obs
```
