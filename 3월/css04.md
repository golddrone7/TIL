# CSS

- 좋은 행동 -> 칭찬 -> 좋은 결과
- 나쁜 행동 -> 비난, 비판 -> 나쁜 결과
- 건수를 만들지 마라
- 애니메이션, Flex Box
- Float을 이용한 페이지, Flex를 이용한 페이지
- 크몽, 웹 템플릿으로 프로젝트 진행
- 템플릿을 미리미리 만들거나 fork 따오기

## 애니메이션

- 적당히 사용하면 생동감이 있을 수 있음
- 과하게 사용하면 별로임
- 잘만든 애니메이션(오픈 소스)
### basic
- (1) keyframes grow-up  애니메이션 이름을 적어줌
- (2) 0% {} 50%{} 100%{} 구간을 정해줌   0~100%까지 애니메이션이 진행.
- (3) 각각의 구간별로 픽셀, 색을 정해줌 
- (4) 적용하고자 하는 애니메이션에 hover를 걸어줌
- (5) `animation-name : grow-up; animation-duration:2s; animation-iteration-count: infinite; animation-delay : 1s; animation-timing-fuction : linear;` 이름 지정, 2초에 걸쳐 애니메이션 진행, 애니메이션 몇번 반복할지, 딜레이 1초 지정, 애니메이션 속도를 지정
- 애니메이션 이름, 몇초에 걸쳐 진행할 지는 필수 속성

### direction
- 애니메이션 방향을 지정
- `animation-direction`의 속성들
- `normal` 0~100%로 움직인다(기본값)
- `reverse` 100%~0%
- `aternate` 0%~100%~0%
- `alternate-reverse` 100%~0%~100%
- 반복횟수가 1번일경우 alternate 속성이 먹히지 않음!

### fill-mode
- 이걸 모르면 난감한 상황
- Game Over 
- 새로 고침을 누르면 다시 원래 위치인 0,0을 가짐
- 이걸 해결하기 위해 fill-mode 속성 사용
- 애니메이션 전후 위치를 설정
- `animation-fill-mode: ;`속성들
- `none`은 기존 위치로 이동(기본값)
- `forwords`는 애니메이션 완료 후 그자리 멈춤
- `both`는 애니메이션 시작 위치, 끝위치 멈춤

### play-state
- 애니메이션을 중지하고 싶을때 사용
- `animation-play-state : paused;`
- hover 될 때 중지
- 0~100%는 `from{} to{}`를 쓰자

## Flex-box
- 정렬하고자 하는 대상의 부모에게 속성을 줌

### 등장배경
- float clearfix문제
- inline-block??? 의도치 않은 공백문제

### Container
- 정렬대상인 item들을 감싸는 요소

### basic
- `display: flex` 부모한테 display:flex 속성을 줌
- 즉 수평 배치하는 대상의 부모에게 속성을 줌

### flex-flow
- 자식들의 가로 길이를 비율을 줄여서 행 유지
- 행렬 레이아웃을 만들 때 방해
- `flex-wrap:nowrap;` 기본값이 속성이라 그럼
- 행렬 레이아웃을 만들 때는 부모 컨테이너에게
- `flex-wrap:wrap;` 속성을 지정하자
- `flex-direction: row;` 수평배치 되는 방향이 left
- `flex-direction: row-reverse;` right 효과
- `flex-direction: column;` 반응형 웹에서 사용, 수직 배치로 변경할 때
- `flex-direction: column-reverse`
- wrap과 nowrap의 차이
- 단축 속성 `flex-flow: wrap row-reverse;`


### 주축정렬
- 주 축과 교차 축, 시작점과 끝점
- `flex-direction : row;` A B C 배치되는 방향을 주축이라 함(수평선) 가로 주축, 세로 교차축, 시작점과 끝점이 좌 우
- `flex-direction : row-reverse` 시작점과 끝이 우 좌
- `flex-direction : column;` 주축이 세로, 교차축이 가로
- `justify-content`는 수평정렬이 아니고 주축 정렬임!!!! 매우 중요
- `justify-content:flex-start` : 시작점에 붙힘
- `flex-end` : 끝점에 붙힘
- `center` : 주축 중앙에 붙힘
- `space-between` 사이사이 마진만: 
- `space-evenly` : 사이사이, 양옆의 마진이 균일
- `space-around` : 요소마다 마진을 균일하게 가짐
- 사용할 마진이 없을 경우 적용안함
- justify는 주축정렬!!!!!!!!!!!(매우 강조)

### 교차축정렬
- `align-content: start;`
- `stretch`는 아이템들을 늘리는 것
- 주의사항, 아이템들의 height px(고정픽셀)을 지정하면 늘어나지 않음
- `align-items` 한줄 일땐 차이가 없지만 두줄 이상일 때부터 `align-content`랑 차이가 남
- `align-content`는 덩어리로 센터로 몰아버림
- `align-items`는 한줄한줄을 개별적으로 봄, 가상의 중앙선을 그어 정렬을 함
- 줄별로 몰아서 할 것인가, 따로할 것인가에 따라 다름
- 일반적으론 `align-items`를 주로 사용

### 응용
- 텍스트 중앙 정렬을 하고자 할 때는 item에 `display : flex`와 `align-items : center; justify-content: center;` 속성을 지정하자

### order
- 개별속성, 아이템 속성
- 아이템들의 배치 순서를 바꿀 때
- 마크업 순서 상관 없음
- `.item:nth-child(2){ order:1;}`
- 실제 정렬대상인 아이템에 거는 속성
- `.item:nth-child(4){order:-1;}`
- 높을수록 뒤로 밀려남
- 모든 아이템들의 기본값은 0

### flex-grow
- 개별속성, 아이템 속성
- float를 할 때는 박스의 크기를 지정을 해야했지만 flex-grow는 비율 나누기를 간편하게 함
- `.item1{flex-grow: 1;} .item2{flex-grown:2;}`
- 문제점, 아이템의 width가 기본 값이 150px일 경우 1:2:1을 지정을 하고 +150px을 함
- 따라서 `flex-basis: 0;`를 빼줘야함
- 한번에 하는 방법 `flex: 1;` 단축속성을 쓰자
- `flex`의 단축속성은 `flex-grow와 flex-basis` 포함
- 즉!! `flex:1`을 써주면 basis값은 0이 된다
- 응용 방법 : header에 3형제가 있음(로고, 메뉴, 검색) 2:5:1, 모바일 태블릿 컴퓨터 비율이 안깨짐

### align-self
- 개별 아이템마다 정렬
  

## css_template_company

### fontawesome
- 아이콘 이미지 제공 사이트
- 주의사항! 문서랑 버전을 잘 봐야함
- 버전마다 class이름이 다름
- 아이콘 사이즈는 폰트 사이즈로 변경
- 색도 폰트 칼라로 변경
- 모바일에서 주로 쓰는 햄버거아 이이콘(bars)
- 회원가입 (user)

### .wrap
- 특정 브라우저가 body를 없어지는 브라우저가 있음
- body 대용으로 전체를 감싸는 한번 더 묶어줌

### header
- .inner-header는 마진을 편하게 넣기 위해 사용
- .gnb global navigation bar
- .tnb 
- 햄버거 바 `display:none` 반응형 웹
- img 태그, 이미지 맞추는 방법 (1) 액자의 사이즈를 지정 (2)가로 사이즈를 지정하면 cover효과가 남 width:100%
- 흰글씨는 text-shadow 쓰자

### 고스트 버튼 애니메이션
- 버튼 창문이 있으면
- after 가상 요소로 커튼을 만듬(복제본)
- position absolute로 겹친다 
- 버튼은 투명, 커튼은 색이 있음
- 커튼의 가로 길이를 0으로 뺌
- 커튼에 마우스 hover를 했을 때 가로 길이를 100으로 늘림 transition!
