# Ubuntu Plugins
 이 문서에서는 동아리 프로젝트 개발에 유용한 우분투(리눅스) 설정 및 플러그인, 프로그램 등을 소개합니다. 백엔드 개발자라면 반드시 리눅스와 함께 아래 플러그인들을 설치하기를 권장합니다.

## System
### 한글 키보드
🔗 [Ubuntu 20.04 키보드 한글 입력 설정 하기](https://shanepark.tistory.com/231)  

### KDE Plasma


## Zsh
&nbsp;zsh은 리눅스 기본 bash 보다 다양한 확장 기능을 제공하는 터미널 쉘입니다. 터미널 테마와 자동완성, 텍스트 하이라이트 등 유용한 플러그인 덕분에 개발에 필수적이라 할 수 있습니다. Zsh은 Mac OS의 기본 터미널 쉘이기도 합니다.  
**설치방법**: 🔗 [Install and Setup ZSH on Ubuntu Linux](https://itsfoss.com/zsh-ubuntu/#install-zsh-on-ubuntu)
```bash
// zsh 설치 및 첫 환경설정
$ sudo apt install zsh git fonts-font-awesome
$ zsh          // 주로 0번이나 1번 선택
$ which zsh    // 설치여부 확인

// zsh을 기본 쉘로 설정 (-s = 특정 쉘로 설정)
// 설정 이후 재로그인 또는 재부팅 필요
$ chsh -s $(which zsh)
```
### Oh My Zsh
&nbsp;OMZ는 Zsh에 다양한 부가 기능을 추가 및 관리해주는 플러그인입니다. 대표적으로 자동완성, 간편한 명령어 별명 기능 등이 있습니다. 아래 커맨드라인을 통해 설치가 완료되면 ```.zshrc```가 업데이트되며, 자동으로 OMZ가 반영됩니다.  
**설치방법**: 🔗 [Oh My Zsh Installation](https://github.com/ohmyzsh/ohmyzsh/tree/master#basic-installation)
```bash
// OMZ 설치용 쉘 스크립트 다운로드 및 실행
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```

### 플러그인 (Auto Suggestion, Syntax Highlight, ...)
![image](https://github.com/ApptiveDev/.github/assets/51331195/98b9c881-5707-4f52-b1e1-6a15eade34b1)

**설치방법**
- 🔗 [Auto Suggestion](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)
- 🔗 [Syntax Highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)  
```bash
# 기본 플러그인 폴더에 Auto Suggestion, Syntax Highlight 소스코드 다운로드
$ git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh 환경설정
$ vi ~/.zshrc

# .zshrc 내에서 플러그인 활성화 및 저장, 종료
plugins=( 
    # other plugins...
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
)

# zsh 새로고침
$ source ~/.zshrc
```

## Program
### pinta (화면 캡처)
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