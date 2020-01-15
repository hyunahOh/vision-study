# Computer Vision Study

## 1. ruby 환경 세팅

컴퓨터에 이미 ruby 가 설치되어 있을 수 있습니다.

```bash
ruby -v
```
이 명령을 치고, 이미 설치되어 있다면 [다음 단계](#second)로 넘어갑니다.

### Windows
윈도우는 아직 모르겠음..

### Linux
```bash
sudo apt-get install ruby-full
```


## <div id="second">2. Jekyll, bundler 설치하기<div>
### Windows
윈도우는 아직 모르겠음..

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