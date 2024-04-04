# css header 영역

## 1. html 태그 작업

### 1.1. anchor 태그

- `<a href="보여줄 페이지 주소"> 글자 </a>`
- `<a href="보여줄 페이지 주소"> 그림 </a>`
- `<a href="보여줄 페이지 주소" target="_blank">사이트명</a>`
  : 새 탭으로 보여주기 (`target="_blank"`)

### 1.2. img 태그

: 파일명.jpg, 파일명.png, 파일명.gif, 파일명.svg
: tip 1. 1순위는 .png
: tip 2. 프론트엔드는 .WebP (Next.js의 기본)
: 상식 : gif 는 여러장의 이미지를 일정 시간 교체해 애니매이션화 하여 하나의 이미지로 만든 파일

-`<img src="경로/파일명.확장자" />` -`<img src="경로/파일명.확장자" alt="이미지설명"/>`
: 이미지 설명이 있는것이 보기 좋다.

## 2. css 선택자

### 2.1. 범위 안쪽에 있는 태그 찾기

```css
.header-logo-slide img {
  ....;
}
.header-logo-slide a {
  ....;
}
```

### 2.2 flex 기초

: container (상자)

```css
.header-logo-link {
  display: flex;
  /* 세로 중앙 */
  align-items: center;
  /* 가로 왼쪽 정렬 */
  justify-content: flex-start;
  /* 가로 가운데 정렬 */
  justify-content: center;
  /* 가로 우측 정렬 */
  justify-content: flex-end;
  /* 가로 양쪽 균등 정렬 */
  justify-content: space-between;
  justify-content: space-around;
}
```

: item (요소들);
