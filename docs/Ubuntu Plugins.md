# Ubuntu Plugins
 이 문서에서는 프로젝트 진행에 유용한 우분투(리눅스) 설정 및 플러그인, 프로그램 등을 소개합니다.

## System
### 한글 키보드
🔗 [Ubuntu 20.04 키보드 한글 입력 설정 하기](https://shanepark.tistory.com/231)  

### KDE Plasma


### Zsh
&nbsp;zsh은 리눅스 기본 bash 보다 다양한 확장 기능을 제공하는 터미널 쉘입니다. 터미널 테마와 자동완성, 텍스트 하이라이트 등 유용한 플러그인 덕분에 개발에 필수적이라 할 수 있습니다. Zsh은 Mac OS의 기본 터미널 쉘이기도 합니다.  
**설치방법** 🔗 [Install and Setup ZSH on Ubuntu Linux](https://itsfoss.com/zsh-ubuntu/#install-zsh-on-ubuntu)
```bash
// zsh 설치 및 첫 환경설정
$ sudo apt install zsh git fonts-font-awesome
$ zsh          // 주로 0번이나 1번 선택
$ which zsh    // 설치여부 확인

// zsh을 기본 쉘로 설정 (-s = 특정 쉘로 설정)
// 설정 이후 재로그인 또는 재부팅 필요
$ chsh -s $(which zsh)
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
