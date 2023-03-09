a# CSS

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