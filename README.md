# JS 11장

```txt
일반 변수는 값이 보관되고    값이 복사된다.

    객체 변수는 주소가 보관되고 주소가 복사된다.
    : 중요한 것은 객체를 복사하는 것은 주의하자. (얕은복사)
    : 가능하면 객체는 깊은 복사를 활용하도록 노력하자.
```

# 깃 협업 (반드시 순서를 꼭! 지켜주세요.)

# JS 12 장

```txt

원시 데이터        ===> 단일 값
복합 데이터 : 복잡한 속성, 메서드를 가진 객체 ===> function, [], {}.

함수는 객체 의 문법을 따르는 값이다.


    function 함수이름(매개 변수) {
      return 문장을 작성 (값을 반드시 출력 : 표현식!!)
    }

    함수이름(인자)  :  함수 호출, 함수 실행, 함수 콜..


    리터럴은 JS 가  알아먹을 수 있는 데이터 형태로 작성한 것
    const a   = 1;             숫자 리터럴
    const add = function() {} ; 함수 리터럴


    const 더하기 =  function (){
    }
    console.log(더하기)  ???


    JS 의 일급객체에 대해서 말해 보시오.

    1. 값처럼 변수에 할당할 수 있는가?
      const add = function() {}

    2. 객체의 프로퍼티의 값으로 담을 수 있는가?
      const obj = { add : function(){}}

    3. 배열의 값으로 담을 수 있는가?
       const arr = [1, 2, 3, 4, function(){}, {}, [] ]

    4. 함수의 매개변수 값으로 전달할 수 있는가?
       function 말해봐(기능) {
           기능();
       }

       const 안녕 = function(){
        console.log("안녕하세요")
       }
       말해봐(안녕)


       말해봐( function(){ console.log("반가워요") } )

   - 함수가  객체를 생성하는 함수를 객체 생성자 함수 라고 합니다.

   - JS 의 함수에 전달되는 매개변수 목록을 arguments 라는 객체 라고 한다.

   - 함수의 매개변수로

     1. 원시 값을 인자로 전달하는 경우

     const age = 15;
     function grow( _value ) {
         return _value + 5;
     }

     grow(age);

     age 는 변화가 없다.


     2. 객체를 인자로 전달하는 경우 (정말 조심해야 해요)
     const person = { age: 10 }

     function growObject(_who) {
         _who.age = 150;
     }

     // 객체의 참조(주소) 값 전달
     growObject(person);

     // 객체의 상태가 변경이 일어난다.



     - 중첩 함수

        function Outer (){

            const handelClick = () => {

            }

            handelClick();

            return ( JSX 구문)
        }

     - 콜백 함수

        window.addEventListener( "이벤트글자", function(){ } )


     - 순수 함수
       function add(a, b) {
          return a + b;
       }

     - 비순수 함수
        const age = 10;
       function add( b) {
          return age + b;
       }
```

# JS 13장

```txt
스코프(scope) : 대상을 사용할 때 찾을 범위
- 대상 :  함수, 변수, 클래스 등...
- var 변수
- let 변수, 또는 const 변수 가 차이가 큽니다.

   // 설명으로 바깥쪽 (함수의 바깥쪽) 를
   // 통상 `전역(global) 스코프`라고 합니다.

   var age = 15;

   function say() {
      // 통상 `지역(local) 스코프`라고 합니다.
      console.log(age)
      console.log(name)
   }

   say(); // ?



   // 설명으로 바깥쪽 (함수의 바깥쪽) 를
   // 통상 `전역(global) 스코프`라고 합니다.

   var age = 15;

   function say() {

      var age = 100;
      console.log(age)
   }

   say(); // ?



   var var_1 = 1;
   if(true) {
      var var_2 = 2;

      if(true) {
        var var_3 = 3;
      }
   }
   function say() {
      var var_4 = 4;
   }
   console.log(var_1)
   console.log(var_2)
   console.log(var_3)
   console.log(var_4)

   렉시컬 환경 (실행과 작성위치)

   JS 는 렉시컬 스코프 를 기본으로 합니다.

   : js 는 대상이 코딩 즉, 작성할때 스코프가 정해진다.
   : 즉, 그때 그때(실행할때 마다) 스코프가 달라지지 않는다.

   var age = 15;

    function say() {

            age += 1;
       var id = "hong";
    }

    say();

    - 앞으로 살펴볼 내용 예습

   let age = 1;

   if(true) {
      let age = 2;

      if(true) {
         let age = 3;
      }
   }
   function gogo() {
      let age = 100;
   }

   console.log(age)
```

# 리액트 프로젝트 환경 세팅

**1 . 사전준비**

- node.js 설치 (nvm 을 통해서 버전 교체 가능)
- npm 은 자동으로 설치되지만 yarn은 직접 설치하여야 함
- github에 repository 생성
- 피그마를 통한 기획

**2 . 프로젝트 생성**

- 폴더명은 소문자로 생성
- 리액트 프로젝트
  `npx create-react-app ./ --template typescript`

**3 . 진행순서**

- public 폴더에 www 폴더 생성 후 퍼블리싱 작업 진행 및 테스트
- React js 버전으로 진행 (CSR)
- React ts로 변경 진행 : js → ts 로 변경 진행
- Next js 버전으로 진행 (SSR) 예정

**4 . 프로젝트 내용 기본 파악하기**

**4.1. node_modules**

- npm 또는 yarn 으로 다운로드 받은 파일 보관 폴더
- 용량이 크므로 github에 push 대상에서 제외하기 위해 .gitignore 에 자동 입력 되어 있음
- npm install 라이브러리명을 이용하여 다운로드 받고 활용
- 참고 : 프로젝트가 라이브러리 등의 오류가 발생했다면
  `node_modules` 폴더 삭제, `package-lock.json` 파일 삭제 후 `npm install` 재실행

**4.2. public 폴더**

: 압축을 하면 webpack 에서 제외되기 때문에 절대 압축을 하면 안된다.

- **public/index.html 파일**
  : 최초 웹서비스 실행시 실행되는 파일명으로 `파일명 변경 불가`
  : `lang=”ko”` 수정
  : `favicon 아이콘` 수정
  : SEO 관련 내용은 별도 추가(네이버검색, 구글검색, GA4 적용 예정)
  : `apple-touch-icon` 수정
  : `title` 내용 수정
  : `manifest.json` 은 추후 내용 수정 필요 (https://web.dev/articles/add-manifest?hl=ko)
  : `id="root"`는 리액트 미리보기 및 결과물이 배치되는 장소

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <!-- SEO 적용 필요 : 네이버 검색 및 구글 검색 등록 예정, GA4 예정 -->
    <meta name="description" content="카카오 브레인 블로그 클론 코딩" />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <title>카카오 브레인블로그</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

- **public/menifest.json**

````json
: manifest.json

- https://web.dev/articles/add-manifest?hl=ko

```json
{
  "short_name": "카카오 브레인 블로그 클론코딩",
  "name": "카카오 브레인 블로그 클론코딩",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}
````

````

- **public/robots.txt**

    : 검색 엔진 로봇이 내용을 접근해서 보관하는 여부 설정

    : 상세 경험은 네이버 및 구글 검색 엔진 등록시 실습


**4.3. src 폴더**

: webpack 의 대상폴더

- **src/index.js**

    : 리액트 실행시 최초 실행되는 파일


```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <App />
);
````

- TDD 관련 파일 제거 (Test Driven Develop : 테스트 주도 개발)
  : App.test.js / setupTests.js
- 성능 측정 파일 제거

  : reportWebvitals.js

- **src/App.js 는 최초 화면에 보여지는 내용이다.**

**4.4. .gitignore 파일**

- 깃허브 파일 예외 사항 기재
- 폴더 및 파일을 작성하면 제외됨.
- 추후 내용 작성 필요(예 : 인증키)

**4.5. package-lock.json**

- node_modules 에서 사용된 라이브러리들의 버전 보관

**4.6. package.json**

- node.js 프로젝트 생성시 기초 정보 관리내용

```jsx
    // dependencies 에서 삭제

    "dependencies": {
    "@testing-library/jest-dom": "^5.17.0",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",

    "web-vitals": "^2.1.4"
    }
```

- dependencies 항목이 중요하다.
  : 프로젝트에 실제 활용한 라이브러리 목록(파악용도)
  : 개발 / 최종 빌드한 소스에 포함이 되는 라이브러리들 목록
  : `npm start` 개발 시 포함

      : `npm build` 배포시 포함
