# CSS

## 목차
<ol>
<li><a href="#a">수도 클래스 선택자</a></li>
<li><a href="#b">상속과 우선순위</a></li>
<li><a href="#c">Box 속성</a></li>
</ol>

## CSS 선택자
- 생각할게 많음
- CSS 수많은 속성들을 안다고 해도 응용을 하기 힘듬

---

<div id="a"></div>

### 1. 수도 클래스 선택자
- 선택해서 옵션을 줌
- 짝수번째, 첫번째, 마지막, n번째 선택
- Git tab, 자동완성, emmt 완성을 활용하자 (생산성 향상)
- ` #fruits li:first-child` id가 fruits를 가진 후손 li 태그의 첫번째
- ` #fruits li:last-child` id가 fruits를 가진 후손 li 태그의 마지막 번째
- `#fruits li:nth-child(3)` id가 fruits를 가진 후손 li 태그의 3번째
- `#fruits li:nth-child(2n+1)` id가 fruits를 가진 후손 li태그의 홀수 번째
- > n에 0부터 순서를 대입했을 때 나오는 숫자의 위치 요소를 선택
- `#fruits li:nth-child(odd)` 홀수번째
- `#fruits li:nth-child(even)` 짝수번째
- `#fruits li:not(.orange)` #fruits의 후손 중에 .orange가 아닌 li 태그
- `nth-child` <b>주의사항</b>, CSS 해석 방식은 아래와 같다
- `.main p:nth-child(3)` main클래스 후손인 셋째 중에 p태그면 적용해라
<br><br><br>
- `before, after` 는 가상 선택자
- `h1{hello}` emmet, h1태그 사이에 hello text 삽입
- `H$*3` h1~h3태그 세개가 생성, `$`는 sequence를 의미 (1~n)
- `before` 는 대상 태그의 앞에 태그를 생성
- `after` 는 대상 태그의 뒤에 태그를 생성
- > 활용 예시 : 고스트 버튼, 투명 버튼, after에 가상버튼을 사이즈 0을 만듬 두개를 겹침 마우스가 hover했을 때 커튼을 만드는 것
- 태그를 붙일 수도 있고 텍스트를 붙일 수 있음
- CSS3은 수도 클래스 선택자에 `::` (before, after 태그)를 권장함 `:`도 가능
- `li::before`,`li::after`는 필수 속성으로 content가 필요
- 도형을 만들기 위해서는 `display` 속성이 필요!!
- > li태그 위|아래에 가상의 li가 생겨서 content가 붙어서 이어 붙이는 방식
- CSS 선택자는 워낙 다양하다, 정답이 없음

---
<div id="b"></div>

### 2. 상속과 우선순위
- 모르면 큰일남
- CSS, 부트스트랩을 가져다 썼는데 마음에 들지 않아 커스텀을 해도 적용이 안되는 상황이 발생
- 우선순위 개념이 있어야 이해 가능
- 부모요소에 적용한 스타일이 후손 요소들까지 영향을 주는 특성, 모든 속성이 상속이 되지 않음
- 상속이 적용되는 속성들 font, text 속성 (글자관련 속성)
- 상속이 쓰이는 이유는 편의성
#### 우선 순위의 규칙
- 인라인 > 아이디 > 클래스 > 태그
- 명시도 점수가 높은 선언이 우선
- !important : 무한대점 `color: blue !important;`
- 인라인 스타일 : 1000점
- 아이디 선택자 : 100점
- 클래스 선택자 : 10점
- 태그 선택자 : 1점
- 전체 선택자 : 0점
- 점수가 같은 경우 가장 마지막에 해석되는 선언이 우선
- 가상요소는 after,before 1점이 부여, 나머지 nth-child는 10점 부여
- 크롬 f12 검사에서 Elements Styles에서 취소된 CSS를 확인해보기 (디버깅), 개선 방법을 찾자 
- 선택자 족보가 화려할 수록 점수를 더하는 방식
- 무한대점 + @ 도 우선순위를 가질 수 있음!

---

<div id="c"></div>

## 3. Box 속성
- 블록 요소에서 사용
- 1개의 박스를 제어하는 속성을 먼저
- 다음은 레이아웃

### 단위
- px, %
- px단위는 픽셀이라는 뜻, 화면에 고정적인 길이를 의미 절대적인 수치
- 1px은 디바이스마다 고정크기가 다를 수 있음
- % 단위는 부모요소 대비 비율적 영향을 받음 (상대적)
- 화면 크기에 따라서 px은 달라서 불편함, 유지보수 측면에서도 불리
- %는 자기 부모의 크기에 비례한다
- body는 항상 100% , body자식은 body 대비 60%
- 특별한 경우가 아니면 고정보다 비율로 설정하자(가로스크롤 문제)

### em, rem
- em은 폰트 사이즈 대비 영향을 받음
- `width : 40em; font-style : 20px` 일 경우 40*20 = 800px로 설정
- em은 자기 자신의 font-size를 알기 힘들 때가 있음
- rem은 `html` 폰트 사이즈 대비 크기
- `html{font-size:10px;}` 을 설정한 다음 
- `{width: 40rem;}` 일 경우 40*10 = 400px 을 말함
- `body{font-size:15px;}` 글씨 크기가 작아져서 보완

### vw, vh
- 뷰포트, 비율 설정
- 반응형 웹을 만들 때 사용 ex) 깃허브
- `<div>` 가로의 기본값 100%, 세로의 기본값 auto
- auto는 컨텐츠의 높이나 가로를 말함
- `{height : 50vh;}` 어떤 디바이스를 들어가도 화면의 절반을 차지
- `{height : 100vh;}` 백그라운드 이미지를 넣을 때 사용
- `body{ margin : 0 , padding : 0}` reset이란 개념
- `body`는 어느정도 css가 들어가있음, 여백의 미
- `vw` 는 뷰포트 가로를 의미, `vh` 는 뷰포트 세로를 의미

### width, height
- width는 요소의 가로를 설정
- height는 요소의 세로를 설정
- 둘 다 지정하지 않았을 경우 기본값은? auto
- width의 auto는 100%를 의미하고
- height의 auto는 컨텐츠의 높이를 의미
- 신경 써야할 부분, 주의할 부분
- > 부모의 높이를 픽셀로 고정값을 넣을 경우 자식이 더크면 깨짐<br>
  > height는 auto로 쓰는 경우가 좋고, 기본 값은 auto 즉! 안쓰는 것이 좋음
- body는 화면 전체를 말함
- 자식은 항상 부모대비 크기를 적용

### max-width, min-width, max-height, min-height
- 이해하기 쉽지 않음
- 최소한 어느정도까지만 줄이는 것이 `min-height`
- 최대한 어느정도까지지 늘리는 것이 `max-height`
- ex) 일정 관리, to-do List
- 화면이 너무 없어보이지도 않게, 깨지지도 않게 하기 위해 사용
- 콘텐츠의 수가 증가하거나 줄어드는 것의 최대, 최소 길이를 유지
- 제한이 걸리는 역할 (부모, 자식) 크기
- 최대 길이보다 넘을 경우 스크롤이 생성


### margin
- 여백을 의미
- margin은 콘텐츠간에 여백
- top, right, bottom, left
- margin으로 빈 줄 효과도 쓸 수 있음
- 기본값 0
- 값을 %로 지정하면 부모요소의 width의 비율로 여백을 가짐
- `margin-left : 37.5%; margin-right : 37.5%;` 가운데 정렬을 쉽게 쓰면
- `margin-left : auto; margin-right : auto;` 박스가 x축 중앙정렬됨 
- 좌우마진을 auto로 지정하면 center
- alt 방향키(위, 아래) 코드 블록 이동
- 단축속성 `{margin : 20px;}` ,`{margin : 30px auto;}`
- 중앙정렬 공식 `{margin : 0 auto;}` 
- >주의사항 : 부모의 사이즈랑 자식의 사이즈가 동일할 경우 중앙정렬이 되지 않음<br>
    분배할 사이즈를 지정을 해줘야함
- text-align과 margin center는 다른 개념이다
- `margin: 0 auto;` 는 부모박스 안에서 자식박스의 x축 중앙정렬 필수적으로 자식의 가로가 부모보다 작아야 여유마진을 분배할 수 있음
- `text-align : center` 는 박스 안에서의 텍스트 중앙 정렬
- 텍스트와 박스를 같이 중앙 정렬을 하고 싶으면
- text는 인라인이고 박스는 블록이다

### padding
- 박스 안쪽의 여백을 설정
- 부모에 margin이 들어가면 자식도 따라서 움직임
- 부모에 padding으로 자식을 밀어내면 커짐 (박스에 패딩을 입으면 커짐)
- 전체적인 박스의 크기가 커진다
- 문제가 생길 여지가 있음
- 부모 컨테이너가 있고 자식 컨테이너 3개가 수평배치가 되어있음
- 부보 가로 1000px 자식 가로 330px (990px)
- 자식에 오른쪽 패딩을 50px로 부여하면 가로가 380px이 됨
- 총 (1140px) 부모보다 자식의 합이 커서 화면이 깨지게 됨
- 패딩을 준 만큼 사이즈를 내려야함 
- 패딩, 보더로 가로 세로가 변하는걸 방지하는 속성
- [공식] `box-sizing : border-box;` default option
- `* { box-sizing: border-box; }` 전체 속성으로 지정하면 padding값의 크기 변화에 대처 가능
- 예시) 폴라로이드 사진 (네이버는 카드 디자인 레이아웃으로 구성)
- `.card{}  .card .img-box{}` 실무TIP)유지보수 측면, 속한 것의 의미
- TIP) 만들때는 색을 입혀서 얼마만큼의 영역을 차지하고 있는가 

### border
- border는 박스 테두리 선을 의미
- border-width 굵기
- bodrder-style 스타일
- border-color 색
- `border` 도 `box-sizing`을 하지 않으면 크기에 영향을 미침
- `border : 1px solid yellowgreen;` 단축속성, 순서는 상관없음
- `border, padding`은 박스 사이징에 영향을 미침
- `*{box-sizing:border-box;}`를 전역 속성으로 꼭 해주자 
- solid, dashed, dotted, groove, double ...
- `box-sizing :content-box` 는 박스 사이즈에 padding, border가 더해짐

### CSS reset 개념
- normalize, 정규화
- html 태그에 기본적인 CSS가 있음
- 구분하기 위해서 적음
- CSS는 백지에서 하는 것이 좋음
- 스타일링 하기 전에 기본 디자인을 싹 빼고 시작함
- reset 파일을 새로 먼저 만듬
- 인터넷에 reset 파일을 적용하자
- `<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">`
- 커스텀 CSS를 적용하고자 하면 아래에 작성하자
- 라이브러리 CSS 불러 올 때도 리셋 밑에다가 적어야함
- 동점일 경우 아래에 있는 것이 적용되기 때문 (우선순위개념)
- 즉 reset -> library > custom 순으로 배치하자

### display 속성
- 요소가 화면에 보여지는 특성을 지정
- 대부분은 block 속성
- 텍스트, 강조는 인라인 속성
- inline-block 인라인 요소이면서 가로, 세로 너비 지정 가능 img, input, button 태그
- none 요소를 사라지게 함
- ex) 댓글 접기, 할일 삭제...
- 기타 : flex, grid
- `display:none;` 은 완전히 사라짐
- `opacity:0;`은 투명도       0: 안보임 1 : 보임
- 사라지고 위에서 올라가게끔 하면 `display:none`
- 스스륵 사라지거나 나타나게 할거면 `opacity`


### overflow
- 박스 안에 내용물이 넘칠 때 제어
- 넘치는 부분을 제어
- 정말 많이 쓰임
- 부모에게 쓰이는 속성
- `overflow:hidden` 넘치면 숨긴다
- `overflow:scroll` 넘치면 스크롤(가로, 세로)
- `overflow:auto` 자동으로 스크롤(가로 or 세로) , 넘칠때만 스크롤
- hidden은 왜 쓰는 걸까?
- 숨겨서 얻을 수 있는 이득이 무엇일까
- 프로필 사진 영역
- 카카오 프로필 사진은 동그라미, 실제 사진은 네모
- 동그라미 바깥쪽 부분은 hidden으로 처리함
- 이미지는 사이즈에 모두 다 맞을 수가 없음
- 세로 크기나 가로 크기 중 100%로 맞춰놓고 버릴 부분은 버리자
- `overflow : hidden;` `height: 100%`

