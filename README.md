# 프로젝트 생성

## 1. 기본사항

- 깃허브에 먼저 소문자로 프로젝트명을 만든다.
- 깃허브에 설명은 반드시 작성한다.
- pc 에 동일한 소문자로 폴더를 만든다.

### 1.1. 리액트 및 퍼블리싱 프로젝트 생성

- 개발환경 구성
  : https://jolly-okapi-f67.notion.site/c9ac2c8354674479b29eb3a1d4a77330?pvs=4
- vscode 필수 설치해주기
- git 초기세팅
  : https://jolly-okapi-f67.notion.site/Git-88e834fe234f4965828e32e0111f6625

- VSCode 를 실행한다.
- PC에 만든 폴더를 드래그 해서 등록한다.
- 명령어를 통하여 기본 파일럿 프로젝트를 생성한다.
  : `npx create-react-app ./` 를 실행한다.
  : Node.js 권장 설치버전 (https://nodejs.org/en/download)
  : Node.js 는 v20.12.0(LTS) 버전을 선택하자.
  : 설치는 기본폴더 그대로 설치하자. 손대면 오류발생 가능.
  : 만약 npm 오류가 발생했다. (-4058 Error)
  :`npm uninstall -g create-react-app`
  :`npm install -g create-react-app`
  : 위처럼 오류 발생시 위의 사항을 실행하고 난 후
  : `npx create-react-app ./` 를 실행한다.

### 1.2. 테스트 해보기

- `npm run start` 실행해보기
- `ctrl+C` 로 미리보기 종료한다.

## 2. 작업순서 기준

### 2.1. 웹서비스 개발 순서(프론트)

- 퍼블리싱부터 진행
- 리액트 진행(필요시)
- 타입스크립트 진행(필요시)
- Nest.js 진행(필요시)

### 2.2. 퍼블리싱 해보기

- 생성된 폴더 최상위를 `Root` 라고 부른다.
- 코드 상으로는 ` /` 로 표현합니다.
- 퍼블리싱은 ` /public` 폴더에 `www` 폴더 생성 후 진행
- 퍼블리싱 기본 폴더 생성 진행
- `www` 폴더 안에
  : images 폴더 생성(.png, .jpg, .gif, .svg)
  : css 폴더 생성 (.css 파일들을 보관)
  : js 폴더 생성 (.js 파일들을 보관)
  : assets 폴더 생성 (문서, 동영상, 디자인원본(.psd))
  : index.html !!파일로!! 생성

### 2.3. index.html 기본구성

- `! 누르면서 Tab 키를 선택`하면 html 기본형이 제공된다. (snap shot)
- lang="en" 은 "ko"로 수정한다.
- 최소 title 은 변경한다.
- 미리보기 (html 파일에서 마우스 오른쪽 클릭 Open Width Live Server)

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>카카오 브레인 블로그</title>
  </head>
  <body></body>
</html>
```

### 2.4. html 문서 작업 순서

: html은 무조건 소문자로 작성해야 함.

- 디자인 레이아웃 보기
- https://chromewebstore.google.com/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl
  : 디자인 파일은 /public/www/assets 폴더에 보관
- html 의 태그의 활용 이전에 꼭 체크 해 보자.
: https://caniuse.com/
<!-- 태그 사용해도 되는지 체크하는 사이트 -->
- 디자인을 살펴보고 영역을 구분하는 작업 진행
  : 레이아웃을 위한 영역 (div 태그)

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>카카오브레인 Blog</title>
  </head>
  <body>
    <!-- 전체 레이아웃 -->
    <div class="wrap">
      <!-- 상단 레이아웃 -->
      <div class="header"></div>
      <!-- 메인 레이아웃 -->
      <div class="main"></div>
      <!-- 하단 레이아웃 -->
      <div class="footer"></div>
    </div>
  </body>
</html>
```

: 내용별 배치 영역 (시멘틱 태그 활용 추천)
: 태그가 내용을 설명하는 역활을 시멘틱

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>카카오브레인 Blog</title>
  </head>
  <body>
    <!-- 전체 레이아웃 -->
    <div class="wrap">
      <!-- 상단 레이아웃 -->
      <header class="header"></header>
      <!-- 메인 레이아웃 -->
      <main class="main"></main>
      <!-- 하단 레이아웃 -->
      <footer class="footer"></footer>
    </div>
  </body>
</html>
```

- (div)에서 상단(header), 메인(main), 하단(footer)로
  구분지어 주었음

- 참고사항 (아래 케이스를 코딩컨벤션이라 하고 사람마다 스타일이 다름)
  : camelCase(카멜케이스) 단어가 변경 될 때 대문자로 구분
  : PscalCase(파스칼케이스) 대문자로 시작해 단어가 변경될 때 대문자로 구분
  : snake*case(스네이크케이스) 소문자로 시작해 *로 단어 변경될 때 구분

- div 구조를 이용해서 뼈대를 잘 만드는 것이 실력
  :<div class="wrap">내용</div> 이 무조건 기본이다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>카카오브레인 Blog</title>
  </head>
  <body>
    <!-- 전체 레이아웃 -->
    <div class="wrap">
      <!-- 상단 레이아웃 -->
      <header class="header">
        <!-- 상단 로고 -->
        <div class="header-logo"></div>
        <!-- 상단 메뉴 -->
        <div class="header-navi"></div>
      </header>
      <!-- 메인 레이아웃 -->
      <main class="main">
        <!-- 메인 상단 -->
        <div class="main-top">
          <!-- 슬라이드 -->
          <div class="main-top-slide"></div>
          <!-- 타이틀 배너 -->
          <div class="main-top-banner"></div>
        </div>
        <!-- 메인 하단 -->
        <div class="main-bottom">
          <!-- 메인 리스트 영역 -->
          <div class="main-bottom-list">
            <!-- 새글 리스트 -->
            <div class="main-bottom-list-news"></div>
            <!-- 배너 -->
            <div class="main-bottom-list-banner"></div>
            <!-- 추천글 리스트 -->
            <div class="main-bottom-list-picks"></div>
          </div>
          <!-- 메인 카드 영역 -->
          <div class="main-bottom-cards">
            <!-- 카드 슬라이드 -->
            <div class="main-bottom-cards-slide"></div>
          </div>
        </div>
      </main>
      <!-- 하단 레이아웃 -->
      <footer class="footer">
        <!-- 하단 사이트 정보 및 사이트 맵 -->
        <div class="footer-top">
          <!-- 회사소개 -->
          <div class="footer-top-info"></div>
          <!-- 사이트맵 -->
          <div class="footer-top-sitemap"></div>
        </div>
        <!-- 하단 카피라이터 및 SNS 링크 -->
        <div class="footer-bottom">
          <!-- 카피라이터 -->
          <div class="footer-bottom-copyright"></div>
          <!-- SNS 목록 -->
          <div class="footer-bottom-sns"></div>
        </div>
      </footer>
    </div>
  </body>
</html>
```

## 3. Git 기초 명령어

### 3.1. 깃으로 관리할거에요.(초기화 : 처음 한번만 함)

- `git init`

### 3.2. 깃으로 관리하는 파일을 추가해두기 (매일, 필요시)

- `git add .` - github 사이트에 명령어는 `git add README.md` 라고 되어있는데 git add 뒤에 있는 파일만 저장한다는 뜻임. 전체 저장해야하니 `git add .`라고 명령함.

### 3.3. 깃으로 작업 내역을 기록해 둔다.(메모 매일, 필요시)

- `git commit`

### 3.4. 깃을 깃허브로 업로드 한다.

- `git remote add 이름 http 주소`
- `git remote add origin https://github.com/LEEAHJEONG/blog-kakaobrain-leeahjeong.git`
- `git remote -v` (저장이 잘 되었나 확인하는 단계 fetch, push 두가지로 뜸, 처음 한번만 하면 됨)

### 3.5. 깃을 깃허브로 push 후 퇴근한다.(매일, 필요시)

- `git push -u origin main`

### 3.6. 브랜치(나뭇가지-코드분기) 나누기

- `git branch 이름`
- `git branch 01-css-basic` 엔터

### 3.7. 브랜치 목록보기

- `git branch` 엔터
-
