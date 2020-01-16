# Computer Vision Study

## 1. ruby 환경 세팅

컴퓨터에 이미 ruby 가 설치되어 있을 수 있습니다.

```bash
ruby -v
```
이 명령을 치고, 이미 설치되어 있다면 [다음 단계](#second)로 넘어갑니다.

### Windows
1. [RubyInstaller 다운로드 페이지](https://rubyinstaller.org/downloads/)에서 Ruby+Devkit 버전을 다운로드 받아 설치하세요.
2. 시작 메뉴에서 명령 프롬프트 창을 열고, 환경변수 `PATH` 를 적절히 설정하세요. \
(참고 : https://jekyllrb-ko.github.io/docs/windows/)

### Linux
```bash
sudo apt-get install ruby-full
```


## <div id="second">2. Jekyll, bundler 설치하기<div>
### Windows
```bash
gem install jekyll bundler
```

### Linux
```bash
sudo gem install jekyll bundler
```

## 3. 로컬에서 Jekyll 블로그 테스트하기

Clone this repository: 
```bash
git clone https://github.com/hyunahOh/vision-study.git
```

Move into that directory:
```bash
cd vision-study/
```

Install required gems using `bundle`:
```bash
bundle install
```

Run the blog in localhost
```bash
bundle exec jekyll serve
```

`http://127.0.0.1:4000`에 접속해서 확인할 수 있습니다.

## 4. Github Pages에 배포하기

이미 배포한 repository이기 때문에 내용 수정 후, `https://github.com/{username}/{projectname}` push해주면 `https://{username}.github.io/{projectname}`에 몇 초 후에 자동으로 배포됩니다.

## 5. 글 포스팅 및 수정하기

### 새로운 글 작성하기
1. `docs/chapter**/` 내에 markdown문서를 새로 생성해줍니다.

2. 문서의 시작부분에 아래의 형태로 작성해줍니다. 뒤에는 markdown포맷에 맞게 글을 작성해주시면 됩니다.
```
---
layout: post
title: "제목"
author: 작성자이름
---
```

3. `_layout/home.html`에 아래의 코드를 추가해주면, 홈 화면에서 새로운 포스팅에 링크를 걸 수 있습니다.
```
<li><a href="{{ site.baseurl }}/docs/챕터/파일명">제목</a></li>
```
참고로 `name.md`라는 파일일경우 `name`부분만 `파일명`으로 넣어주시면 됩니다.

## Some issues to konw

1. `bundle install`명령어 입력 후, Nokogiri설치 중 에러가 났다는 메시지가 발생
> An error occurred while installing nokogiri (1.10.7), and Bundler
cannot continue.
Make sure that `gem install nokogiri -v '1.10.7' --source
'http://rubygems.org/'` succeeds before bundling.

위와 같은 에러가 발생하면
```bash
sudo gem install nokogiri
bundle config build.nokogiri --use-system-libraries --with-xml2-include=/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/libxml2
```
라고 입력 후 다시 `bundle install`해주면 된다.