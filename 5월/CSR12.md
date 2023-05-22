# CSR12

## 

- 개발배경
- 개발기간
- 개발목표
- 개발기능
- 개발내용
- 역할분담

## SPA
- html 페이지가 딱 1개
- 태그를 지웠다 넣었다함
- 최적화에 특화된 프레임워크가 React

## React
- DOM, AJAX, rendering 최적화
- 개발된 프레임워크의 일종
- Vue.js, Angular.js, Popper.js...
- 업무를 완벽하게 분리할 수 있음
- SOAP + REST = X
- SPA 특징은 C <-> S 최초 한번만 일어남
- index.html 하나만 받고 ajax로 통신함
- 다음부턴 fetch만 보냄
- 화면 전환도 스스로 일어남
- npm  node js package manager


### 라이브러리 의존성 관리
#### 등장 배경
- 없던 시절엔 일일이 사이트에서 다운로드를 받았어야 함
- 자기 프로젝트에서 라이브러리 폴더를 만들어서 넣었어야함
- 충돌 이슈가 있을 수 있음
- 깃허브에 라이브러리도 올리면 무거워짐
- 프로젝트 실행할 때 다운로드 받기 때문에 관리에 용이함
- 버전 관리
- npm install -g create-react-app
- `-g` 옵션은 전역에 설치한다는 의미임
- 자바 진영은 maven central
- 자바스크립트는 npm
- packange.json 이 build.grandle같은 것
- 백엔드 프로젝트 따로
- 프론트엔드 프로젝트 따로
- 배포도 다른 서버에 따로해야함
- 백엔드의 종속에서 벗어남
- 파이썬이어두 됨
- `npm start` 시작
- 프론트 3000번 리액트 서버 
- 백엔드 8080번 스프링 서버
- 마리아DB 3306번
- 라이브 서버 5500번
- index.html와 index.js는 커스텀하지말기
- app.js 등등은 커스텀 해도 됨
- `<>` fragment
- return값은 하나의 부모만 감싸야함
- html 문법과 jsx문법의 차이점
- className, htmlFor...
- `SayHello.js` 와 같이 앞 문자가 대문자일 경우 리액트 컴포넌트구나
- 요즘 대세는 함수형 컴포넌트임
```jsx
import React from "react";

function SayHello(){
    return (
            <div>
                <p>안녕</p>
                <span>메롱</span>
            </div>
    ); 
}


export default SayHello;
```
1