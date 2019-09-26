---
title: "Homebrew 로 Mac 한 방에 셋업하기"
description: 언제까지 Mac 설정에 하루 종일 시간을 쓸 것인가?
categories: [Tool]
tags: [Tool, Setting, Mac]
author: JSon
redirect_from:
  - /setting/2019/08/18/brew_cask_mas.html
  - /tool/2019/08/18/brew_cask_mas.html
---

안녕하세요, 힐링페이퍼에서 백엔드를 담당하고 있는 제이슨입니다!\\
사용자가 불편함 없이 빠르고 안정적으로 더 좋은 의료 서비스를 이용할 수 있도록 하는 역할을 하고 있습니다.

회사에 첫 출근! 을 하고 Mac 을 딱 받으면, 이런 생각 들지 않으시나요?\\
"아 이거 또 언제 세팅하나"\\
"이전에 뭐 설치해서 쓰고 있었더라?"\\
"그냥 타임머신으로 옮겨와 버릴까?"\\
"그래도 새로 받은거 깔끔하게 다시 설정하고 싶은데..."

이런 고민, 개발자들이 평소에 Mac 에서 사용하고 있는 **[Homebrew](https://brew.sh/)** 를 이용하면 깔끔하게 해결할 수 있습니다!

<figure>
  <img src="/assets/images/json/2019-08-18_1.png" class="center" width="40%">
  <figcaption>
    수제맥주가 땡기는 날씨입니다.
  </figcaption>
</figure>

Homebrew 는 Mac 에서 개발하는 사람이라면 대부분 사용하고 계실 유명한 패키지 매니저 입니다.\\
(package manager: 소프트웨어 패키지를 쉽게 설치하고 관리할 수 있게 도와주는 툴)

이 Homebrew 에 잘 알려지지 않은 기능으로 **cask** 가 있습니다.\\
cask 를 이용하면 평소에 웹사이트에 찾아가 다운로드 받던 어플리케이션(ex. Google Chrome)을 쉽게 설치할 수 있습니다.

거기에 **mas** 까지 이용하면 앱스토어에서 받을 수 있는 어플리케이션(ex. 카카오톡)도 쉽게 설치할 수 있습니다.

정리해보면 아래와 같습니다.

- Homebrew: 개발 관련 패키지 설치
- cask: 웹사이트에서 받을 수 있는 어플리케이션 설치
- mas: 앱스토어에서 받을 수 있는 어플리케이션 설치

# 사전 준비

## Homebrew 설치

Homebrew 가 설치되어있지 않다면 설치해주도록 합시다.

```shell
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## cask 설치

cask 는 Homebrew 최신 버전에 내장되어 있습니다.

## mas 설치

Homebrew 에서 mas 를 설치해주도록 합시다.\\
(사실 이마저도 BrewFile 에 넣어서 설치할 수 있긴 하지만)

```shell
$ brew install mas
```

# BrewFile 로 한 방에 설치하기

BrewFile 에 brew, cask, mas 의 설치 목록을 저장해 놓으면, Homebrew 로 이를 한방에 설치할 수 있습니다.

예제

```yaml
# BrewFile
brew "asdf"
brew "awscli"
brew "git"
brew "mas"
cask "docker"
cask "google-chrome"
cask "visual-studio-code"
mas "KakaoTalk", id: 869223134
mas "Todoist", id: 585829637
```

- **brew**: asdf, awscli, git, mas 등 개발 패키지
- **cask**: Docker, Chrome, VSCode 등 웹사이트에서 다운 받아 설치하는 어플리케이션
- **mas**: 카카오톡, Todoist 등 앱스토어를 통해 설치하는 어플리케이션

이제 BrewFile 이 있는 폴더에서 이 명령 **한 줄**이면

```shell
$ brew bundle
```

BrewFile 파일에 있는 패키지, 어플리케이션 전부 자동으로 설치해줍니다.

끝! 쉽죠?

# BrewFile 만들기

그러면 이런 BrewFile 은 어떻게 만들까요?

현재 사용하고 있는 Mac 에 설치된 항목들을 BrewFile 로 저장하려면 아래의 명령을 수행하면 됩니다.

```shell
# Brewfile 생성
$ brew bundle dump

# 생성된 BrewFile 내용 확인
$ cat BrewFile

brew "awscli"
cask "docker"
...
```

## cask 추가

추가적으로 웹사이트에서 다운로드 받아 설치하는 어플리케이션을 BrewFile 에 추가하려면 cask 에서 검색을 해서 적으면 됩니다.

IntelliJ IDEA 를 추가해봅시다.

```shell
# 정식명칭을 모르니 intellij 로 검색
$ brew search intellij
==> Casks
intellij-idea       intellij-idea       intellij-idea-ce    intellij-idea-ce

# cask 에서 정식명칭이 intellij-idea 임을 확인했습니다.

# 설치하려면 아래와 같이 할 수 있습니다.
$ brew cask install intellij-idea

# BrewFile 에는 아래와 같이 추가하면 됩니다.
cask "intellij-idea"
```

## mas 추가

앱스토어를 통해 설치하는 어플리케이션을 BrewFile 에 추가하려면 mas 에서 검색합니다.

xcode 를 추가해봅시다

```shell
# mas 에서 xcode 검색
$ mas search xcode
  497799835  Xcode                                                                (10.3)
  1183412116  Swiftify for Xcode                                                   (5.0.4)
  1163893338  App School for Xcode and  iOS 10 Development Free                    (1.0)
  ..

# ma 에서 정식명칭이 "Xcode", id 가 497799835 임을 확인했습니다.

# 설치하려면 아래와 같이 할 수 있습니다.
$ mas install 497799835

# BrewFile 에는 아래와 같이 추가하면 됩니다.
mas "Xcode", id: 497799835
```

이제 나만의 BrewFile 을 만들 수 있게 되었습니다!\\
새로운 Mac 을 받게 되면 꼭 한번 시도해보세요.\\
더 이상 환경 설정에 하루 종일 신경쓸 필요가 없습니다.

References

[https://brew.sh](https://brew.sh/)\\
[https://github.com/Homebrew/homebrew-bundle](https://github.com/Homebrew/homebrew-bundle)\\
[https://github.com/mas-cli/mas](https://github.com/mas-cli/mas)

---

힐링페이퍼는 항상 더 좋은 분들과 함께하며 기준을 높여나가고 싶습니다. \\
더 좋은 의료 서비스를 누구나 누릴 수 있게 하는데 함께 하시고 싶으신 분들은 `recruit@healingpaper.com` 로 연락주세요! \\
감사합니다.
