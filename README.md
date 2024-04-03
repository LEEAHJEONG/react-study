# CSS 기초

- html 은 화면에 보여줄 데이터(글자) 입니다.
- css 는 화면에 보여줄 데이터(html)를 보기 좋게 꾸며주는 역활을 합니다.

## 1. CSS 작성법 (4가지)

### 1.1. 인라인 방식 : html에 직접 적용

- <태그 style="이름 : 값">
- 가독성이 떨어진다.
- CSS 코드를 재활용하는 것이 불가능하다.

```html
<body style="background: color(hotpink)"></body>
```

### 1.2. `<style>` 태그 활용하기

- 가독성이 좋다.
- css 코드 재활용이 어렵다.
- 선택자 { css 적용 }
- css Selector { css 적용}

```html
<style>
  body {
    background: hotpink;
  }
</style>
```

### 1.3. 외부파일로 css 분리하기

- 가독성이 좋다.
- 코드 재활용이 좋다.
- 일반적으로 많이 활용한다.
- 예시: css/common.css (확장자는 무조건 .css)

```html
<link rel="stylesheet" href="./css/common.css" />
```

### 1.4. CSS 에 CSS 파일 불러들여서 관리하기

- 대표적으로 글꼴을 @import 해서 사용 (@import `앳 @`은 최상단에 작성)

```css
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap");
body {
  background: green;
}
```

- 참고사항
  : 프로그래밍 언어는 문장의 끝을 표현한다. ( `;` 세미클론)

## 2. css 초기화 하기

### 2.2. 선택을 하자.(코딩 컨벤션)

- https://necolas.github.io/normalize.css/8.0.1/normalize.css
  : 노멀라이즈
- https://meyerweb.com/eric/tools/css/reset/reset.css
  : 리셋
- 우리가 만든 common.css 도 링크하자.
  : 꼭 기억해야 함.`box-sizing: border-box`
  : 필요시 기억해야 함. `outline-style: none;`
- css 코드 배치 순서 정말 중요!
  : 만약 같은 종류라면 작성 순서 기준
  : 가장 우선시 한다면 `!important`
  - (css가 아니고 html 인라인으로 작성했다면 css > html 순서로 적용.)

```css
@charset "utf-8";
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  /* 옵션 */
  /* outline-style: none; */
}
html {
  font-size: 16px;
}
body {
  color: #000000;
}
.wrap {
  width: 1170px;
}
```

## 3. css 로 전체 레이아웃에 적용해 보기

### 3.1. 멘토 및 실무자는 반드시 반응형을 봅니다.

- 화면(디바이스) 너비 관례상 기준
- 기본 화면(1280px 이상)을 먼저 작업한다.

```css
.wrap {
  width: 95%;
  max-width: 1280px;
  margin: 0 auto;
}
```

- 랜탑 화면(1024px) 화면의 레이아웃을 작업한다.

```css
@media screen and (max-width: 1024px) {
}
```

- 타블렛 화면(960px) 화면의 레이아웃을 작업한다.

```css
@media screen and (max-width: 960px) {
}
```

- 고해상도 모바일 화면(760px) 화면의 레이아웃을 작업한다.

```css
@media screen and (max-width: 760px) {
}
```

- 중해상도 모바일 화면(480px) 화면의 레이아웃을 작업한다.

```css
@media screen and (max-width: 480px) {
}
```

- 저해상도 모바일 화면(320px) 화면의 레이아웃을 작업한다.

```css
@media screen and (max-width: 320px) {
}
```

: 완성된 예

```css
.wrap {
  width: 95%;
  max-width: 1280px;
  margin: 0 auto;
}
@media screen and (max-width: 1024px) {
}
@media screen and (max-width: 960px) {
}
@media screen and (max-width: 760px) {
}
@media screen and (max-width: 480px) {
}
@media screen and (max-width: 320px) {
}
```
