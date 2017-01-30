# 애플 유저를 위한 것들

애플 제품은 돈을 넣은 만큼 제 값을 하는 경향을 보이고 있습니다. 뭐, 근데 그게 비례하는 것도 아니고, 엄청나게 비싼 걸 질러야지 값어치를 하는게 대부분이죠. 그 중에서 가성비가 뛰어나고, 써보면 좋은 것들에 대해서 따로 적는 시간을 가져보려고 합니다.

##  앱스토어 앱들

### 한컴오피스 한글 뷰어

### Microsoft Remote Desktop

### Shazam

### Portal

### Dr. Cleaner

### Drive - External Drive Manager

### WiFi Signal

### Duplicate Finder

### Simplenote

### iA Writer

### Pomodoro Time

### Magnet

### Alfred

### 1Password

제일 돈 값을 하는 어플리케이션입니다. 매달 [3 달러](https://1password.com/sign-up/)를 결제하시거나 [싱글라이선스](https://agilebits.com/store)를 $65불에 구매하실 수 있습니다. 패스워드 관리 툴인데, 여러분 제발 패스워드 구글닥스같은데 평문으로 써놓거나 이런저런 웹사이트에서 같은 패스워드 쓰지 마시고 1password로 비밀번호 자동 생성해서 회원가입하고 로그인 할때는 1password로 로그인 합시다. 1password로 로그인 하거나 이런 저런 관리르 하기 위해서는 마스터 비밀번호가 필요합니다. 그것만 외우시면 되요.

### Bandizip X

### Cobook

### Night Owl

### Xccello

## 비-앱스토어 앱들

### Synergy

### Hyper Term

### iTerm

### Disk Inventory X

### Scroll Reverser

### Duet

## Homebrew Cask

### atom

### mccvim

### sshfs

### osxfuse

### vargrant

## [Homebrew](http://brew.sh/)

Debian에 `apt-get`이 있다면, 맥에는 `brew`가 있습니다. 

`brew install <pacakge-name>`

패키지 관리자로 의존성문제를 해결하고 패키지를 최신상태로 유지하세요!

### [mackup](https://github.com/lra/mackup)

맥 한번 백업하려면 SSH 키도 백업해야하고, 각종 쉘이나 에디터 설정도 백업해야하고 .. 너무 번거로우셨죠? 역시나 누군가 백업 프로세스를 스크립트로 만들어 놓았습니다. 드랍박스샅은 클라우드에 환경설정들을 저장하고 불러오게 하는 툴 입니다.

### m-cli

### mas

### ack

### doxygen

### [zsh](http://www.zsh.org/)

bash를 대체하는 쉘 zsh입니다. 
bash와 차이점은

1. 자동완성을 지원해줍니다.
2. 터미널을 여러개 쓰더라도 history가 공유됩니다
3. 디렉토리 자동완성도 지원합니다. 예를들면, `vim /u/l/b/a<Tab>` 을 입력하면 `/usr/local/bin/autoupdate.sh` 를 열어줍니다.
4. 오타를 고쳐줍니다.
5. 등등

fish보다 기본적인 기능은 약하지만 POSIX기반이라 쉘 스크립트가 호환되고 추가기능 설치로 사용성을 높일 수 있습니다.

[oh-my-zsh]를 사용하시면 zsh 테마 입히기도 쉽고, 버전 유지하기도 쉽고, 플러그인 설치하기도 무척 쉬워집니다. zsh 플러그인은 alias set을 지원합니다(예: [기본으로 깔려있는 git플러그인](https://github.com/robbyrussell/oh-my-zsh/blob/master/plugins/git/git.plugin.zsh)). zsh를 바로 다운로드 하시는 것보다 oh-my-zsh를 바로 설치하시는게 여러모로 편리합니다.

### [fish](https://fishshell.com/)

요새 핫한 쉘 fish 입니다. 설정, 스킨, 자동완성, 쉘 신텍스 하이라이팅 등 웬만한 기능이 이미 기본으로 설정되어있기 때문에 추가적으로 커스터마이징을 하지 않더라도 사용성이 매우 좋습니다. 하지만 POSIX 표준이 아니기 때문에 기존 POSIX 쉘(bash, zsh 등)에서 사용하던 스크립트들과 호환이 되지 않습니다. [fish-shell-cookbook](https://github.com/jbucaran/fish-shell-cookbook) 에서 기본적인 튜토리얼을 다루고 있습니다.

zsh처럼 [oh-my-fish](https://github.com/oh-my-fish/oh-my-fish)를 통해서 기능을 확장하거나 테마를 변경할 수 있습니다.

### [python](https://python.org)

맥에 기본적으로 2.7이 깔려있습니다. 파이썬 홈페이지에서 파이썬 3 패키지를 다운로드하거나 brew로 설치 가능합니다.

### ruby

### lsusb

