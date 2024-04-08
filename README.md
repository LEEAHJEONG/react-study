## 0. 배포하기

- ftp : File Transfer Protocol
- http : Hypertext Markup Transfer Protocol
- smtp : Simple mail Transfer Protocol
- [파일질라](https://filezilla-project.org/)
- [무료웹호스팅](https://www.dothome.co.kr/)

# main 영역 html, css

## 1. html

- 레이아웃을 공통적용을 위해서 inner div 작성(header 처럼)
- main-top 과 main-bottom 을 inner 안쪽에 배치
- main-top 클래스에 왼쪽, 오른쪽 영역 잡기

## 2. css

- 화면의 너비 즉, vw를 이용해서 높이에 반영
- 너비와 높이가 같이 변하는 반응형 작성시
  : `보여줄 너비 /나누기 화면의 너비 *곱하기 100 = 결과값 %;`
  : `보여줄 높이 /나누기 화면의 너비 *곱하기 100 = 결과값 vw;` -웹사이트가 보이는 영역을 viewport 뷰포트 라고 한다. -뷰포트는 전체를 100vw(화면너비를 100등분)와 100vh(높이를 100등분)로 값을 줄 수 있다.

- 모서리를 둥글게
  : `border-radius: 20px;`
- 내용 일부 가리기
  : `overflow: hidden;`

- 배경에 이미지 넣기
  : 그림깔고 내용 위치 잡기
  : 그림깔고 내용 위치잡기
  ```css
  .main-top-banner a {
    display: block;
    width: 100%;
    height: 100%;
    background-image: url("../images/br.png");
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
  }
  ```
  :축약형
  ```css
  background: url("../images//br.png") no-repeat center;
  background-size: contain;
  ```
  - 좋아요
  ```css
  .main-top-banner a {
    display: block;
    width: 100%;
    height: 100%;
    background: url("../images/br.png") no-repeat center;
    background-size: cover;
  }
  ```
