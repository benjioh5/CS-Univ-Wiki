# 리눅스

## 리눅스란?

[리누스 토르발즈](https://ko.wikipedia.org/wiki/%EB%A6%AC%EB%88%84%EC%8A%A4_%ED%86%A0%EB%A5%B4%EB%B0%9C%EC%8A%A4) 가 개발한 오픈소스 커널의 이름이다.
또한 이 커널을 이용한 모든 운영체제를 지칭하여 리눅스 라고도 한다. 리눅스 커널은 오픈소스 프로젝트 이고, 공식 페이지는 [이곳](http://kernel.org) 이다. 오픈소스 프로젝트 인만큼 전세계 많은 개발자들이 리눅스 커널의 업데이트에 기여 하고 있다. 

리눅스 커널을 기반으로 하여 만들어진 운영체제를 리눅스 배포판이라고 한다. 현재 사용 목적과 환경에 따라 만들어진 200여 종이 넘는 리눅스 배포판이 존재하며, 안드로이드 또한 리눅스 배포판의 한 종류라고 볼 수 있다. [여기](https://distrowatch.com/) 에서 각 배포판들의 순위를 확인 할 수도 있다.

## 라이선스

리눅스는 GPLv2 (GNU General Public License 의 버전2) 라는 라이선스를 아래에서 개발되고, 배포 되어진다. 따라서, 소스코드가 공개되며, 개발자가 필요에 맞게 소스코드를 수정 하는 것이 가능하다. 

## GUI 환경

보통 리눅스 하면 떠오르는게 콘솔이나 터미널에서 명령어를 이용해서 작동하는 것을 상상 하게 되는데, 리눅스 또한 GUI 환경을 구성하여 일반 데스크탑 용도로 충분히 이용 할 수 있다.

[X 윈도우 시스템](https://ko.wikipedia.org/wiki/X_%EC%9C%88%EB%8F%84_%EC%8B%9C%EC%8A%A4%ED%85%9C) 이라는 것을 이용해서, 입력 장치들과의 상호작용을 통해서 화면에 창을 그린다.

데스크탑 환경을 구성하는데 기본 X 윈도우 시스템을 가지고는 너무 투박 할 수 있다. 그래서 보통 X 윈도우 시스템 위에 다른 윈도우 매니저나, 데스크탑 환경을 설치하여 사용한다.
윈도우 매니저는 창의 최소화, 최대화, 리사이징 등을 구현하는 프로그램이라고 보면 되고, 데스크탑 환경은 윈도우 매니저를 기본으로 포함하고, 그 위에 편의를 위한 프로그램들이 더 있는 환경이라고 보면 된다.

이게 윈도우 매니저 (Window Manager) 와 데스크탑 환경 (Desktop Environment) 의 [차이](http://askubuntu.com/questions/18078/what-is-the-difference-between-a-desktop-environment-and-a-window-manager) 이다.

### 윈도우 매니저의 종류

스택형

- [Fluxbox](http://www.fluxbox.org/)
- [Compiz](https://launchpad.net/compiz)
- [Blackbox](http://blackboxwm.sourceforge.net/)

...

타일형

- [Bspwm](https://github.com/baskerville/bspwm)
- [i3](http://i3wm.org/)

...

### 데스크탑 환경의 종류

- [GNOME](https://www.gnome.org/gnome-3/)
- [KDE Plasma](https://www.kde.org/workspaces/plasmadesktop/)
- [Xfce](http://www.xfce.org/)

...

## 윈도우와 다른점

### 실행 파일 구조 

리눅스는 ELF (Executable and Linkable Format) 라는 실행 파일 구조를 사용하는 반면, 윈도우는 PE (Portable Executable) 구조를 이용 한다. 두 실행 파일 구조는 호환이 안되므로, 당연히 윈도우 프로그램을 리눅스에서 실행 시키거나, 반대의 경우도 할 수 없다.

물론 아예 할 수 없는 것은 아니며, 리눅스의 경우 윈도우 API 를 에뮬레이팅 시켜주는 [wine](https://www.winehq.org/) 이라는 프로그램을 사용하면 가능하다.

## 리눅스 배포판 

### [우분투 (Ubuntu)](https://www.ubuntu.com/)

> 요즘 리눅스를 설치한다고 하면 열에 아홉은 설치하는 배포판. 그정도로 쉽고, 편리하다.

데비안 계열의 리눅스 배포판, [마클 셔틀워스](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC_%EC%85%94%ED%8B%80%EC%9B%8C%EC%8A%A4) 라는 사람이 설립한 __캐노니컬__ 이라는 주식회사 에서 우분투 리눅스의 프로젝트를 진행하고 있다. 또한 마클 셔틀워스 본인이 우분투 개발의 지휘자라고 알려져 있다.

데비안 계열의 리눅스 배포판인 만큼 패키지 관리자는 [dpkg](https://ko.wikipedia.org/wiki/Dpkg) 를 사용한다. 또한 [apt](https://ko.wikipedia.org/wiki/%EC%96%B4%EB%93%9C%EB%B0%B4%EC%8A%A4%ED%8A%B8_%ED%8C%A8%ED%82%A4%EC%A7%95_%ED%88%B4) 라는 고급 패키지 툴을 이용하여 저장소에서 쉽게 어플리케이션을 받아 설치 할 수 있다.

처음 리눅스를 접한 사람들 또한 별다른 어려움 없이 설치 할 수 있을 정도로 쉽다. 데스크탑 버전을 위한 우분투를 설치하면 [Unity](https://ko.wikipedia.org/wiki/%EC%9C%A0%EB%8B%88%ED%8B%B0_(%EC%82%AC%EC%9A%A9%EC%9E%90_%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4)) 라는 유저 인터페이스가 설치 된다. 이 이외에 서버 버전 우분투도 있으니 참고.
    
우분투는 배포판에 대한 수정이나, 재배포가 자유로워서 우분투를 기반으로한 다른 배포판들이 많이 있다. 

우분투의 버전번호는 보통 (배포하는 년도).(배포하는 월) 로 구성되어 지는데, 예를들어 현재 최신버전인 16.04 는 2016 년 4월에 배포가 진다는 뜻이다. 

또한 각 버전별로 코드명도 하나씩 가지고 있는데, 보통 (형용사 + 동물이름) 으로 구성 되어진다. 예를들어 16.04 의 경우 Xenial Xerus, 14.10 의 경우 Utopic Unicorn 이라는 코드 명을 가지고 있다.

### [아치리눅스 (Archlinux)](https://www.archlinux.org/)

리눅스 커널을 기반으로 한 롤링 릴리즈 (Rolling release) 방식의 리눅스 배포판이다. 현재 지원하는 아키텍쳐는 i686 과 x86_64 를 지원 하고 있지만 i686 의 경우 곧 지원이 [중단](https://www.archlinux.org/news/phasing-out-i686-support/) 될 예정이다. 

아치 리눅스의 슬로건이 Keep It Simple 인 만큼, 설치 부터 세팅까지 손수 CLI 환경에서 사용자가 설정해야 한다는 것이 특징이다. 이점은 매우 귀찮은 부분이 될 수 도 있지만, 커스터마이징을 좋아하는 유저들이나, 리눅스를 전반적으로 익혀볼 유저들에게는 좋은 이점으로 작용 될 수 있다.

pacman 이라는 공식 저장소를 사용하는 패키지 관리자가 있고, 써드파티 저장소라고 볼 수 있는 [AUR](https://aur.archlinux.org/) 를 이용 할 수 있는 yaourt 라는 패키지 관리자가 있다.
