# CSS

## 목차
<ol>
  <li><a href="#a">글꼴, 문자 </a></li>
  <li><a href="#"> </a></li>
  <li><a href="#"> </a></li>
</ol>

---
- inherit 상속

<div id="a"></div>

## 1. 글꼴, 문자

### font-size
- 폰트의 크기
- px, em(16px)
- % 부모 요소의 비율로 지정

### font-weight
- 폰트의 굵기
- normal(400), bold(700)
- bolder 부모 요소보다 두껍게
- lighter 부모 요소보다 더 얇게
- 숫자 100-900
- 폰트 제작자가 400, 700만 만들었을 경우 다른 굵기는 지정못함
- font-family에 따라 상속된 값이 다름 
- Google Fonts는 free
- 상용 폰트는 저작권 위험이 있음

### font-family
- 폰트 글꼴
- 글꼴 후보1, 후보2, 후보3, 글꼴 계열(필수), serif : 바탕체
- `font-family: '바탕체', candy, 'Red Hat Mono', serif;`
- 인터넷 환경에 따라 폰트 다운로드 받는 시간이 다름
- 필요한 CSS와 폰트를 다운로드 받음
- 후보 폰트중에 먼저 있는 것을 적용한 다음 바탕체 다운로드가 완료되면 완료!
- 이마저도 없으면 serif 먼저 적용함
- serif 바탕체 sans-serif 필기체 cursive 필기체(궁서체), monospace 글자의 가로폭이 동일한 계열(프로그래머 사용), fantasy 판타지(화려한 계열)
- 


### color
- 글자 색상은 그냥 color
- 색상 이름을 yellow, red 이런식으로 지정하지 말기
- 크롬, 익스플로러, 파이어 폭스가 생각하는 yellow가 다 다름
- 브라우저마다 해석하는 방식이 다름
- 컬러 코드 16진수 또는 rgb 계열로 쓰자
- 웹은 촌스럽게 만들지 말기
- 중요한 요소
- `.c1 {color: #00ff00;}`
- `#aa66cc -> #a6c` 자동으로 바꿈
- `rgb(1,1,255)`
- `rgba(211,29,181,0.6)` a값을 조정해서 그라이데이션 효과를 줄 수 있음

### line-height
- 행간의 개념보다 줄 높이
- 줄높이
- 한 줄의 높이를 말함
- 행간을 pixel로 주기 보단 1.5 배수로 주면 됨
- `line-height: 1.5;`
- 1.2~1.6이 이상적인 줄 높이
  
### text-align
- 문자 정렬 방식
- 기본 값이 left
- left, center, right
- 기사같은 내용은 justify 옵션이 좋음(2줄 이상일 때 적용)

### text-decoration
- 글자 꾸미는 용도
- 취소선, 밑줄, 윗줄
- a태그는 기본적으로 밑줄이 들어가있음
- overline, underline 
- `color : red;`
- 밑줄의 색상을 글자와 다르게 바꾸고 싶으면 border-bottom 으로 처리함 
- `border-bottom: 2px solid blue; width: fit-content; margin: 0 auto; `

### indent
- 글자 들여쓰기
- `text-indent : 10px` 10px 만큼 들여쓰기, -로 주면 내여쓰기

### letter-space, word-space
- 자간, 단어간
- 하나의 글자, 특정한 곳만 뛰어쓰기를 하고 싶으면 `&nbsp;`를 쓰자
- `            word-spacing: 5px;
            letter-spacing: 10px;`

---

## 2. 배경
- 브라우저는 명시적으로 img 태그를 삽입하는 방식과 CSS로 삽입하는 방식이 있음

### background
- 단축속성
- background-color 색상 넣을 때
- 이미지 넣을 때 많이 사용
- ` background-image: url(../../img/sky.jpg);` bgi 
- img 태그는 사진이 삐져나와 `overflow : hidden` 으로 처리해야 하지만 css로 background 속성을 시키면 자동으로 overflow hidden을 해줌
- img태그와 background 속성 두개의 차이를 기억
- `background-size : 80px 50px;` 
- `background-repeat` 속성은 기본값이 repeat
- `background-repeat: no-repeat;` 설정해주자
- 사이즈값을 가로만 주면 세로는 비율 조정
- `background-position : 30px 100px;` x축 30px, y축 100px 만큼 이동, 미세조정할 때 사용
- `background-position: right top;` right, center, top
- ` background-position: 0% 100%;` 0% 0% 왼쪽 위 100% 100% 오른쪽 아래
- 단축속성 `background`를 사용할 때 포지션 / 사이즈 순서를 지키자!
- center(위치) / cover(사이즈)
- `background: url(../../img/hobak.jpg) orange no-repeat 150px 100px / 20px 100px;` 
- `background-size: cover;` 가로, 세로 사이즈중에 손해를 덜 보는 쪽으로 cover함
- `background-size: contain;` 손실이 없지만 액자에 빈 공간이 있음
- 가장 좋은 방법은 포토샵을 작업 한 후 사이즈를 맞춤
- 대부분의 웹은 cover로 작업하자

### background-attachment
- 스크롤을 내리거나 올려도 고정적으로 붙힘
- `background: url('../../img/sky.jpg') no-repeat center/cover fixed;`
- ex) 스타벅스 사이트 원두
- 이미지를 특정 위치에 넣는 방법
- 0) 리셋 작업
- 1) 패딩으로 공간을 확보하기
- 2) 이미지 넣기
- 3) 위치 설정, 반복 설정하기
- 4) `background: pink url(../../img/bg_line.gif) repeat-x left bottom;`


## 3. 박스띄우기
- 레이아웃 
- 고전적인 방법
- 귀찮음, 옛날 핸드폰 느낌
- 생각할것, 신경할게 많음
- 웹을 공부할 땐 하위호환을 신경써야 함(보수적 개발)
- 9장 flex box는 특정 웹에선 잘 안됨
- Grid는 너무 최신 기술이라 하위호환이 잘안됨 실무에서 잘 사용하지 않음
### float 
- 요소를 좌우 방향으로 띄움(수평 정렬)
- `display:inline-block`의 문제점: 알수없는 마진이 등장함 이상한 마진이 포함
- 이상한 마진의 정체는 뛰어쓰기
- 정렬하고자 하는 것을 `float: left`를 설정하자
- `.box:nth-child(3n+1){
            /* 수평 정렬 해제 */
            clear: left;
        }`
- 3열 레이아웃은 `3n+1` x열 레이아웃은 `xn+1`
- 공식1 텍스트 중앙 정렬 `text-align : center;`
- 공식2 y축 중앙 정렬 `line-height: 150px;` 줄높이랑 일치시키면 y축 중앙 정렬
- float는 고정적인 레이아웃에선 문제가 없지만 가변적인 레이아웃에선 문제가 생김
- 문제점은? z축으로 나옴
- float는 부유하다 
- 부모요소에 가상 클래스를 추가해서 해제
- ```css
  .container1::after{
        content: '';
        display: block;
        clear: left;
        }
  ```
- float가 right일 경우 clear도 right로 바꿔야함
- 둘다 적용하면 `clear: both;`를 권장함!!
- 리팩토링 방법 : 공통 코드는 클래스를 추가해서 만들어주자
- ```css 
  .clearfix::after{
          content: '';
          display: block;
          clear: both;
        }
  .ct {
          width: 700px;
          padding: 20px;
          border: 3px solid;
          margin: 20px;
        }
  .container2{
          border-color: blue;
        }

  .container3{
          border-color: green;
        }
  ```