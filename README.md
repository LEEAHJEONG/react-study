# CSS 최적화

# js syntax 1장 프로그래밍

```txt
1. Syntax (구문) : 약속된 문법
2. Interpreter (번역) : 갤럭시 AI/웹브라우저 
3. 프로그래밍은 요구사항을 분석하고 (개인별로 작성 : 의사코드)
Syntax 를 이용해서
적절한 자료구조와 적합한 함수를 활용하고
흐름을 제어하여 요구사항을 만족시킨다.
```

# js Syntax 코드 위치

1. inline 방식

```html
<div class="wrap" onclick="alert('안녕');"></div>
```

2. 태그 방식

```html
<script>
  alert("반가워");
</script>
```

3. 외부파일 방식 (권장)

   : 내부 js 코드는 무시되기 때문에 2번의 형식으로 나타내야 한다.

3.1

```html
<script src="./js/script.js">
  alert("반가워"); // 실행안됨
</script>
```

3.2

```html
<script src="./js/script.js"></script>
```

# Swiper Slide 적용해 보기 1

- **Slide 를 직접 코딩하지 마세요.**
- 사용법을 배운다고 이해하자.
- [Swiper](https://swiperjs.com/) :
  권장함! 장점- 리액트지원이 된다. 터치지원을 한다. 반응형을 지원한다.
  적용방법: css와 js 주소 html에 넣어주기
  - [Slick](https://swiperjs.com/) : 사용 프로그램에 따라 수정해야 할 부분이 있음
- [BxSlider](https://bxslider.com/) : BxSlider 는 사용하지 않는게 좋다.

## 1. Swiper 슬라이드 적용시 주의 사항

- html 로드 완료 및 이미지 로드 완료 후 실행 권장.

```js
window.addEventListener("load", function () {
  // 실제 슬라이드 코드 배치하자.
});
```

# js 2장 자바스크립트란?

```txt

  mp3  실행하려면? mp3 Player
  .hwp 실행하려면? 한글 Player

   javaScript 뭐지 ?


   publisher : 웹브라우저용 프로그래밍 언어 (html, css 다룬다)
   FE        : node.js (웹브라우저용 pg 아니고, pc 용 프로그래밍 언어)
               서버(dothome... db... html, css ...)

   웹 브라우저 player 마다 다 다르다.
   IE, Chrome, Opera, Safari..... (모두 다 다르다. Syntax )
   예) 메뉴하나를 만들어도 다시 각각에 웹브라우저에 맞게 마이그레이션을 해야.



   ES6

   렌더링 (목표는 html, css, js 로 문서 만들기)

    SSR (Server Side Redering)
     : php, spring (WAS), Next.js

    CSR (Client Side Redering) 이 있어요.
     : React, Vue, Angular ..

    Ajax (아작스, 에이젝스..) : 데이터(json) 통신
      : 비동기 (Request 요청  Response 회신) / 동기 구분
      : XML Http Request (XHR 통신)
      : vanila JS / pure JS (fetch/async await)     <=====>    jQuery (ajax)


      Node.js 하실 수 있나요?
       서버(Express.js), DB(MongoDB, MySql) 가능합니까?

      SPA : Single Page Application
      CBD : Component based Developement

      객체 지향
      : 모든 코드의 시작은 객체로 설계하여 전개한다.

      예) 기획자 : xls 로 제공한다.
          - 인터파크 상품(최상단 배치되는 제품의 정보를 노출)
          - 상품의 기본 정보
           : 할인율, 가격, 제목, 이미지 보여주면 되겠다.
           : 제품상세 정보로 이동하는 경로를 제공

          디자이너
          - UI 및 UX 배치

          BE 개발자
          - 제품의 정보를 DB 저장해둠. (일부만 Response )

          FE 개발자 :
          const Good = {
            ratio : 할인율,
            price : 가격,
            title : 제목,
            pic  : 이미지주소,
            link : 제품주소
          }

          const 객체명 = {
             속성명 : 속성값,
             기능   : function(){ 기능 }
          }


          Const TodoList = () => {
            const gogo = (e) => {
              alert ("클릭")
            }
            return (
               <>
                 <div className="a" onClick="gogo">
                   ~~~~
                  </div>
               </>
             )
          }


      프로토타입 기반 : 프로토타입(유전자)를 상속받아 덧댄다.

      Babel 이란 : 현재 최신 코드를 옛날 코드로 변환해 준다.
```

# Swiper Slide 적용해 보기 2.

- 데모사이트의 core 메뉴를 통해서 참조한다.
- 기본 css와 js파일은 CDN으로 참조한다.

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css"
/>
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
```

- 기본형 코드를 작성해서 원하는 영역에 배치한다.
- 슬라이드 갯수 만큼 swiper-slide div 를 만든다.

```html
<div class="swiper 원하는이름">
  <div class="swiper-wrapper">
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
  </div>
</div>

여기서 변경할 수 있는 것은 원하는이름과 내용 뿐임 swiper에서 제공되는 것은 절대
바꾸어서는 안됨
```

- CSS 로 `원하는이름` 을 찾아서 width, height를 100% 줍시다.
- CSS 로 `원하는이름` 을 절대로 display 등 은 넣으면 안된다. 디폴드값으로 들어가있다.

# Swiper Slide 적용해보기 3.

- 외부 데이터 연동(json)
- 데이터의 구조를 설계
- json이란. jabaScript Object Notation 입니다.

```json

목업데이터, 더미데이터를 만들어보자.
[
  { "키": 값(value), "키": "값(value)", "키": "값(value)" },
  { "id": 2, "pic": "b2.png", "url": "#" },
  { "id": 3, "pic": "b3.png", "url": "#" },
  { "id": 4, "pic": "b4.png", "url": "#" }
]

```

# Swiper SLide 적용해보기 4.

- 비동기 호출하기(vanila/pure js로 해보자)
  : BE 와 협업시 활용한다.
- fetch 를 활용 가능
- async await 활용 가능

# js 3장

```txt
DOM(Document Object Model)
   - html 을 읽고, 수정 등등의 조작을 하는
     함수 (DOM API)
     document.querySelector(".wrap")

    클라이언트 사이드 API
    DOM, BOM, Canvas, XMLHttpRequest, fetch
    requestAnimationFrame, SVG, Web Storage,
    Web Component, Web Worker 등..

    Node.js   설치를 하면 자동으로
    npm 설치 됩니다. Node Package(js 소스) Manager
    https://www.npmjs.com/

    npm install 패키지명@버전
    node -v
    npm -v

    nvm (Node.js 의 버전을 자유롭게 변경하고, 설치)

    yarn install 패키지명@버전
```

# Swiper Slide 적용해 보기 5.

- 외부 js 파일을 이용한다.

```html
<script src="./js/파일명.js"></script>
```

```js
window.addEventListener("load", function () {
  //내용작성;
});
```

- swiper 에 보여줄 데이터를 외부 .json 파일로 연동한다.
  : 자료(데이터)를 만들어주는 동료가 BackEnd 입니다.
  : BE 와 협의가 필요하다. (협업의 기본)
  : 초기에는 가짜데이터(Dummy, Mockup) 을 가지고 작업

```json
[
  { "키명": "키값" }
  { "키명": "문자열" },
  { "키명": 55},
  { "키명": true},
  { "키명": []}
  { "키명": {} }
]
```

```json
[
  {
    "id": 1,
    "pic": "b1.png",
    "url": "#",
    "title": "AI 헬스케어의 <br/> 마일스톤을 찍다"
  },
  {
    "id": 2,
    "pic": "b2.png",
    "url": "#",
    "title": "카카오브레인의 <br/> 연구문화"
  },
  {
    "id": 3,
    "pic": "b3.png",
    "url": "#",
    "title": "PathFinder 2기의 <br/> 언어모델 활용기"
  },
  {
    "id": 4,
    "pic": "b4.png",
    "url": "#",
    "title": "칼로리의 꿈 <br/> 시리즈 ③"
  }
]
```

- json 데이터를 이용해서 자료를 추출한다.
  : 외부 주소를 통해서 자료를 불러들이기 위해 fetch를 알고 적용한다.
  : 더불어서 크롬 개발자 도구(F12)의 NetWork 탭을 알아야 한다.
  : 옵션으로 Fetch/XHR 을 선택할 수 있어야 한다.
  : request 와 response 를 구별하여 파악할 수 있어야 한다.

```js
fetch("주소").then().then().catch();
```

```js
fetch("주소")
  .then((결과) => {
    const 접속괄과 = 결과.jaon();
    return 접속결과;
  })
  .then((최종자료) => {
    // 하고 싶은 일~ 맘대로~
    // 백엔드에서 자료를 받은 후 우리가 할 일을 진행한다.
  })
  .catch((오류) => {
    // 오류처리
  });
```

- 추출된 데이터로 html 을 생성한다.
  : 백틱(``)을 적극적으로 사용한다.

```js
let slideTags = "";

for (let i = 0; i < result.length; i++) {
  const data = result[i];
  // 템플릿 문법 필요 (html)
  const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
  slideTags = slideTags + test;
}
```

: html 을 배치한다.

```js
// 원하는 장소에 출력해 보자.
const whereTag = document.querySelector(".topslide .swiper-wrapper");
whereTag.innerHTML = slideTags;
```

- swiper 를 작동시킨다.
  : html 작성 완료 후 슬라이드를 생성한다.

```js
// DOM 을 다루려고 하는 목적인 경우
window.addEventListener("load", function () {
  // 1. 외부에서 자료를 불러온다.
  const dataUrl = "./apis/topslide.json";

  fetch(dataUrl)
    .then((response) => {
      const data = response.json();
      // 변환된 결과를 돌려주기
      return data;
    })
    .then((result) => {
      // Step 2. json 변경된 데이터 활용하기
      // 전체 글자 모음
      let slideTags = "";

      for (let i = 0; i < result.length; i++) {
        const data = result[i];
        // 템플릿 문법 필요 (html)
        const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
        slideTags = slideTags + test;
      }

      // 2. 자료를 이용해서 슬라이드에 배치할 html 을 만든다.
      // 원하는 장소에 출력해 보자.
      const whereTag = document.querySelector(".topslide .swiper-wrapper");
      whereTag.innerHTML = slideTags;

      // 3. html 완성후 swiper 를 생성한다.
      // 기본코드를 넣어보자.
      var topSlide = new Swiper(".topslide", {});
    })
    .catch((error) => {
      console.log(error);
    });
});
```

# Swiper Slide 적용해 보기 6.

- [옵션](https://swiperjs.com/demos#autoplay)
  : loop
  : autoplay
  : effect
  : speed
  : pagenation(https://swiperjs.com/demos#autoplay)
- 페이지네이션 디자인 작업 참조

```css
.bannerslide .swiper-pagination {
  bottom: 30px !important;
}
.bannerslide .swiper-pagination-bullet {
  width: 4px !important;
  height: 4px !important;
  background: #ffffff !important;
  opacity: 0.7 !important;
  border-radius: 4px !important;
  transition: width 0.3s;
  margin: 0 2px !important;
}
.bannerslide .swiper-pagination-bullet-active {
  background: #ffffff !important;
  opacity: 1 !important;
  width: 20px !important;
}
```

# js 4장

- var 변수명 = 변수값;
- let 변수명 = 변수값;
- const 변수명 = 변수값;

```txt
호이스팅(hoisting) 은 변수, 함수를 선언하지 않았는데도 사용할 수 있다.
```

# css 의 opacity 와 position 의 이해.

- opacity 는 DOM의 내용까지도 투명도가 적용된다.
- position
  : position 중에 absolute 로 픽셀 위치 설정할 경우 주의점
  : 반드시 기준이 될 position 코드가 바깥 영역에도 있어야 합니다.
  : position 중에 fixed는 웹브라우저를 기준으로 배치
  : fixed는 반드시 left, top, right,k bottom을 주자
  : fixed는 보통 z-index를 준다.
  : fixed는 높이 반영이 안된다. (레이아웃 배치 문제)

```css
대상 {
  position: relative;
}
대상 {
  position: absolute;
}
대상 {
  position: fixed;
}
```

: absolute를 사용하려면 relative나 fixed로 기준점을 잡아야하지만
: relative, fixed는 단독사용가능하다.

- 주의사항

```css
.box-wrap {
  // 코드 영역 기준 설정해주기
  position: relative;
  margin: 0 auto;
  width: 600px;
  height: 300px;
  background: orange;
}
.box {
  position: absolute;
  right: 80px;
  bottom: 20px;

  width: 200px;
  height: 200px;
  background: red;
}
```

# js 윈도우 스크롤의 위치를 알아내기

```js
window.addEventLinstenr("scoll", function () {
  // 하고 싶은 일
});
```

```js
window.addEventLinstenr("scoll", function () {
  // 하고 싶은 일
});
```

# js 로 css 의 클래스 동적으로 활용하기

```js
// DOM 찾아서 변수로 레퍼런스 하기
const tags = document.querySelector(".클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가
tags.classList.add("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 제거
tags.classList.remove("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가 / 제거
tags.classList.toggle("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 포함여부
tags.classList.contain("클래스명");
```

# js 의 함수란? 1.

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복이 되지 않아도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하장.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하장.
- 실행의 결과가 그때그때마다 다른 경우에도 함수를 만들자.

```js
// 함수선언(함수만들기)
function 적절한동사() {
  // 하고싶은일 작성...
}
// 함수호출(함수사용하기)
적절한동사();
// 예시 (함수 체이닝)
fetch().then().then().catch();
```

- 함수는 무조건 1개의 값을 리턴하도록 규정되어 있다.
- 리턴이란 함수 실행 후 값을 돌려주는 것을 말한다.

```js
function 함수명() {
  // return 을 작성안해도 알아서 return을 실행해줌
  // return undefined;
}
함수명();
```

# JS 5장

```txt
코딩에서 값이라고 할 수 있는 것은
  변수에 할당(보관한)된 결과를 말한다.

  변수란? 컴퓨터 공간에 이름을 붙여둔 방 한개

  표현식이

  평가(식을 해석해서 값을 생성하고 참조하는 것)된
   결과를 말한다.


   리터럴 이란?
   사람이 이해할 수 있는 문자 또는 약속된 기호를
   사용해서     값   을    생성하는 표기법

   리터럴은 값을 평가해서 코드에 활용하기 위한 문법


  "function"
  var function

  function gg(){}

  표현식 expressioin
  : 리터럴 값으로 평가가 되면 OK!
     5  숫자 리터럴 값으로 평가가 되면 OK!
     "안녕" 문자열 리터럴 값으로 평가가 되면 OK!

     var num = 5;
     var num:number = 5;


  문(statement) :  프로그램을 구성하는 기본단위/최소 실행단위

  {}


  var foo = x = 100
```

# js 의 함수란 ? 2번

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.

- 함수 정의 문

```js
function 함수이름() {
  // 할일
}
```

- 함수 실행(call) 문

```js
함수이름();
```

# js의 함수의 매개변수란? 3번

- 초기 기능 즉, 함수를 정의하기 전에 기능 상 자주 변하는 데이터를 고민한다.
- 기능은 스크롤시 특정 위치보다 커지면 css 추가하기
- 이전 코드는 좋지 않은 코드라고 생각이든다.
- 함수는 스스로 지역(Local) 영역(Scope) 에서 처리되는 것이 좋다.
- 위의 처리라는 말은 변수를 찾거나, 잘못된 값이 전달되어서 오류가 나는 것을 말한다.

```js
// 홍길동에서 줄 함수
const a = 5;
const b = 6;

function sum() {
  return a + b;
}
sum();
```

- 매개변수(parameter)

```js
const 변수명 = 값;
function 함수명(매개변수) {
  // 할 일..
}
```
