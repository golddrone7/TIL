<h1>1. HTML</h1>

## 목차
<a href="#content-tag">1. 콘텐츠 구분 태그</a><br>
<a href="#inline">2. 인라인</a><br>
<a href="#multi">3. 멀티미디어 내장 콘텐츠 태그</a><br>
<a href="#table">4. 표 컨텐츠 태그</a><br>
<a href="#input">5. 입력 양식</a><br>
<a href="#jun">6. 전역 속성</a><br>
<a href="#css">7. CSS</a><br>


## 오늘의 조언
- 공부하는 습관(복습)
- Base 쌓기 
- 블록요소 = 박스(가로랑 세로길이를 가짐)
<hr>
<div id="content-tag"></div>

## 콘텐츠 구분 태그

### 1. h1~h6
- 디자인 하지 말기(글자 크기)
- h1은 하나의 페이지는 하나만
- h2~h6 순서대로 작성하기
### 2. div
- 깡통 태그
- header~footer 쓸 일이 없을 때 쓰기
### 3. ol, ul, li
- ol은 정렬된 목록 (순서가 중요한 목록)
- ul은 정렬되지 않은 목록(순서가 중요하지 않을 때)
> 메일 | 카페 | 블로그 | 지식in | ... 처럼 상관이 없으면 ul태그
- 웹 사이트는 대부분 ul을 씀
- 새로운 것들이 추가되면 ul이 확장성이 높음
- ol과 ul의 자식은 li만 올 수 있음
- li 자식은 여러개 가능
- 링크를 걸고 싶으면 li태그 안에 a 태그 선언하기
  ```html
    <ul>
        <li>
            <a href="#">네이버 링크</a>
        </li>
        <li>양파</li>
        <li>치즈
            <ul>
                <li>체다 치즈</li>
                <li>모짜렐라 치즈</li>
            </ul>
        </li>
        <li>우유</li>
    </ul>
  ```
- li는 단독으로 사용 불가
#### 4. p
- Lorem Ipsum은 아무말 생성
- `<br>`태그는 break 뛰어쓰기, 줄바꿈이 꼭 필요할 때 사용
- `empty`태그는 닫는 태그가 없는 것을 말함(자식을 가질 수 없음)
- p 요소는 하나의 문단을 설정할 때 사용
#### 5. hr
- 문단을 분리 할 때 사용
- 회색선을 넣을려고 사용 하는 것이 아님!

#### 6. 클론코딩
- 구조를 잘 짜는 것이 중요
- (1) 네모를 치기
- (2) 큰 박스, header, main, footer, aside
- (3) 작은 박스, 로고, 메뉴, 제목, 목록, 푸터
- (4) 더 작은 박스 메뉴의 목록, Article1~3
- (5) 더욱 작은 박스 내용 Contnet
- class는 별칭을 말함, div는 별명을 붙이기
- 작성 요령(큰 구조부터 작은 구조)
- div.Container
- header, section.main, footer, aside
- h1, nav
- ul>li*3>a
- article은 잘 사용하지 않음 div.article 형태로 사용

<div id="inline"></div>

---

## 인라인 텍스트 태그

### 1. a 태그
- 앵커는 닷이란 의미
- 페이지를 링크 필수 속성은 href 
- ex) 다른 페이지, 특정 위치, 파일 다운로드 링크, 이메일주소, 목차..
- ` alt shift 아래키` 
- ` alt shift 아래키` 한줄 복사(아래 생성!)
- 특이 사항이 아니면 _black기능은 잘 안씀
- 팝업 기능도 잘 안쓰임 대신 modal 기능 씀
- 절대경로로 링크를 쓰면 오류남 (파일 구조 상 보안에 취약)
- 로컬 리소스를 쓰는데 허락 하지 않음
- 따라서 로컬 경로를 쓸려면 상대 경로를 써야 함
- > 해결 방법 : 상대 경로를 쓴다. 
- 메일 문의, 문의 전화
- 자바 스크립트로 링크 구현 가능
- a태그는 구조적인 의미!!!
  
### 2. abbr 태그
- 약어 표현할 때 사용
- `<abbr title="Cacading Style Sheet">CSS</abbr>`

### 3. 강조 태그
- `strong` 강조 , `br` 뛰어쓰기, `em` 이탈릭체 , `mark` 형광펜
- 모두다 꾸미는 의미가 아닌 <b>강조</b>의 의미를 강조!!!
- 실제 리더기는 강조 태그에 큰 억양으로 말함!

### 4. span 태그
- 강조, 약어가 아닐 때 쓰면됨
- ` <span>동해물</span>` ` span{font-weight: 700;color: red; }` 꾸미는건 CSS

---

<div id="multi"></div>

## 멀티미디어 내장콘텐츠 태그

### 1. img
- empty 태그, 자식이 존재하지 않음
- 이미지 주소 복사
- 노션은 아마존 웹 서버에 저장
- 인라인 속성을 가지면서 가로, 세로 길이가 조절 됨
- `<input>, <img>` 태그는 `inline-block` 속성
- 이미지 태그는 가로세로 중 한쪽만 바꿔도 나머지 부분은 비율적 조정
> 원본 이미지 500 * 500 변경 이미지 가로 200으로 바꾸면 세로 200사이즈<br>
> 원본 이미지 1000 * 500 변경 이미지 가로 200으로 바꾸면 세로 100사이즈

- src는 필수 속성, alt는 대체 텍스트를 의미
- html에도 속성으로 가로 세로길이를 지정할 수 있지만 철저하게 css에 작성하자!

### 2. audio, video
- 쿼리 음성, 영상 파일을 재생
- 귀신 음악 소리같은 악용 소지로 웹에선 많은 제약 사항이 있음
- autoplay...
- 잘 사용하지 않고 iframe으로 대체함

### 3. iframe
- 웹의 콘텐츠를 웹에 삽입하는 방식으로 사용
- ex) 유튜브 소스코드 복사

---

<div id="table"></div>

## 표 컨텐츠 태그
- table > tbody > tr > th + td 구조로 이루어짐
- 게시판 형태를 사용할 때 많이 사용
- 첫 줄에는 열의 정보 특정한 의미가 담김
- 행과 열로 이루어짐
- `table` 태그 안에서 border 지정 하지 말기
- CSS로 작업
- `border-collapese : collapse;` 중복 선 제거
- `<th>` 태그는 1행에서 의미가 있는 데이터로 사용
- table에서 가장 많이 하는 실수!
- `table`의 자식은 `tbody` 자동으로 생성
- 의도적으로 `<tbody></tbody>` 태그를 적어주자
- 셀 병합을 하고 싶으면 `rowspan`과 `colspan` 속성을 사용하자
  
  ---

<div id="input"></div>

## 입력 양식
### 1. form 태그
- 수평 배치, 인라인 블록
- form 태그는 클라이언트에서 서버에 내용을 보내고자 할 때 사용
- 서버에서 입력 데이터들을 검증함
- > ex)food 코트는 한식, 일식, 중식 서버가 있음, 
- 데이터를 들고 넘어가기 위해선 name 속성 필요
- `<input type="text" name="keyword">`
- `http://lalala3213123.com/search?keyword=ddd`
- 서버에 들어가기 위해선 여러가지 요청이 있음
- `<form action="http://lalala3213123.com/search" method="get" autocomplete="off" novalidate></form>` 
- get은 조회 (기본값, default)
- post는 등록, 수정, 삭제 (갱신)   ex)회원가입(민감한 정보, 보안의 목적)
- action 속성 : 이동하고자 하는 url(jsp, servlet ...)
- `autocomplete="off"` 는 자동완성 기능 X
- `novalidate` 는 검증을 하지 않겠다는 의미
- `<input type="email" name="keyword">` 는 이메일 양식이지만, novalidate를 쓰면 검증하지 않고 넘어감
- ```html
    <form action="https://search.naver.com/search.naver" method="get" autocomplete="off" novalidate>
        <input type="name" name="query">
        <button>검색</button>
    </form>
    ```
- git push는 항상 신중하게
### 2. input 태그
- 아직 만들지 않았으면 `"#"` 을 사용하자
- value 속성은 회원가입을 하고 나서 바로 로그인을 할 때 사용한다
- `type="password"`는 자동으로 마킹
- `readonly` 논리 속성 (쓰면 true, 안쓰면 false), 단순하게 뛰울 때만 씀
- html5 이전에는 `readonly="readonly"` 를 명시했다 
- `type="email"`는 이메일 검증이 들어감
- `placeholder="aaa@bbb.com"` 은 입력 힌트를 의미
- `type="checkbox"` 체크박스, 다중 체크 가능 `checked` 속성을 붙이면 체킹
- `disabled` 선점 된 좌석, 물품이 없을 땐 체킹이 안되게 막음
- `type="radio" name="mail"` 라디오, 하나만 선택 가능 ! 그룹 지정을 하기 위해 name을 맞춰줌
- ```html
    <form action="#">
        * 이름 : <input type="text" value="홍길동"><br>
        * 패스워드 : <input type="password"><br>
        * 이메일 : <input type="email" placeholder="aaa@bbb.com"><br>

        * 취미 :
        <input type="checkbox"> 게임
        <input type="checkbox" checked> 축구
        <input type="checkbox" disabled> 낮잠 <br>

        # 메일 수신 여부 : 
        <input type="radio" name="mail"> 예 
        <input type="radio" name="mail"> 아니오 <br>
        
        # 주문 수량:
        <input type="number" max="10" value="1">
        <!-- 기본 태그가 디자인이 별로여서 자바 스크립트로 구현 -->
        # 파일 : 
        <input type="file" multiple>
    
        <!-- 사용자 몰래 서버로 보내야 하는 데이터 -->
        <input type="hidden" name="nickname" value="바보">
        <br>
        <button type="button">그냥 버튼</button>
        <button type="reset">입력값 초기화버튼</button>
        <button type="submit">서버전송버튼</button>
    </form>
    ```
- `type="submit"` 속성은 잘 안쓰임, 비밀번호 검증 같은 처리를 해야 하기 때문
- `type="button"` 자바 스크립트를 활용하여 전처리 작업 후에 진행

### 3. label태그
- label 태그에 작성한 내용도 클릭을 하면 체킹을 하게 만듬
- `<input type="checkbox" id="remember">`
- `<label><input type="checkbox">자동 로그인</label>` 
- `<label for="remember">아이디 기억하기</label>`  물리적으로 떨어져 있어도 작동
- 모바일 특성 상 체킹 박스는 너무나도 작음
- 그러므로 라벨을 통해 묶어주는 방식이 바른 방향
- 기본적인 속성은 인라인 속성

### 4. textarea태그
- 여러줄을 작성 할 수 있음
- row, col 글자수를 지정 가능

### 5. Select 태그
- select 자식은 option 태그
- ```html
    <form action="#">
        <select name="coffee">
            <option value="아메리카노">Americano</option>
            <option value="카페라떼">Caffe Latte</option>
            <option value="카푸치노">Cappuccino</option>
        </select>
        <button>확인</button>

        <input
            type="text"
            name="nick"
            value="홍길동"
            disabled
        >
    </form>

    ```
- `disabled` 는 입력을 막고 서버에도 데이터를 보내지 않음
- `readonly` 는 입력만 막고 서버에는 데이터를 보냄
  

<div id="jun"></div>

## 전역 속성
### 1. class 속성
- 클래스 속성은 별명을 지칭
- 모든 태그에 붙일 수 있고 중복이 가능한 속성 
- 여러개 부여 가능 `class="orange grape"` 2개의 별명을 가짐
- 그룹을 나타날 때 표현
### 2. id 속성
- 식별자
- 아이디는 중복 허용하지 않음
- id는 한 태그 당 1개만 부여 가능 `form id="apple"`
- 모든 태그에 사용 가능
- 하나의 태그를 표현
### 3. style 속성
- 인라인 스타일로 지정 가능
- `<input style="width: 200px;">` 쓰지 않는 것이 좋음
  
### 4. title 속성
- 마우스에 올리면 값을 보여줌
  
### 5. data 속성
- 우리가 커스텀 할 수 있는 속성
- 네이버 `data-dark="false"` 같은 커스텀을 말함


<div id="css"></div>

## CSS
<hr>

## CSS 기초
### 1. CSS 정의
- 레이아웃, 폰트, 색상처리 등의 디자인 요소를 만들기 위한 언어
- 마크업언어로 작성된 문서가 웹 사이트에 표현 방법을 정해주는 언어
- 내부, 외부, 인라인 스타일 시트 3가지 종류
### 2. 인라인 스타일
- 정적인 형태는 인라인 스타일은 쓰지 않는 것이 좋음
- 단점 : 유지보수 하기 힘듬

### 3. 내부 스타일
- html 내에 스타일 적용하기
- 단점 : 여러 페이지에 적용할 수 없음
- SPA (Sing Page Application) -> HTMl이 1개 (페이스북)

### 4. 외부 스타일
- 결론은 외부스타일이 바람직

## 선택자

### 1. CSS Selector
### 2. 전체 선택자
- `*` 전부를 의미함
- `font-family: cursive;` 궁서체
- 모든 태그 하나하나를 의미함
- `body{border: 1px solid #000;}` 는 body 하나만을 의미함
- `*{border: 1px solid #000;}` 은 모든 태그 하나 다 적용함
### 3. 태그 선택자
- `li{}` 모든 li 태그에 스타일 적용
- `list-style:none` 
- `font-size: 1.5em` 상위 요소 크기의 1.5배
- `font-weight: 700` 굵은 글씨
### 4. 클래스 선택자
- `.orange{}` 
- `background: orange;` 백그라운드 색을 오렌지 색상
- li는 블록 속성, span은 인라인 속성
### 5. 아이디 선택자
- `#tomato{ background : tomato;}` 토마토 아이디를 가진 배경 색상이 토마토 색상
- `width : fit-content`
- `transform : rotate(180deg);`
### 6. 일치 선택자
- 동시에 여러 조건을 만족하는 경우
- `li.orange{}` li태그의 클래스 이름이 orange
- `p#tomato{}` p태그의 아이디가 tomato 
- `#apple.reverse{}` id가 apple이면서 reverse 클래스
- ```
    h1.yellow.low.primary#change{
        background: yellow;
       }
     <h1 class="yellow low primary" id="change">안녕하세요</h1>
    ```
### 7. 자식 선택자
- 바로 직속 자식을 선택
- 맨 뒤가 타겟, 앞에는 조건
- `ul > .orange { background:orange;}` ul의 직속 자식인 orange 클래스를 선택
- `body > div > ul > li{color : red;}` body 직속 div 직속 ul 직속 li 태그를 선택

### 8. 후손 선택자
- 후손을 선택함
- 맨 뒤가 타겟, 앞에는 조건
- `div .orange` div 태그 후손의 .orange 클래스를 선택
- `body #tomato` body 태그 후손의 tomato 아이디를 선택
- ``` html
        /* 좋지 않은 코드
        프로그램을 업데이트를 하게 되면 당근의 부모에 섹션이 추가 될 수 있음 */
        .wrap > div{  
            font-size: 1.5em;
            color: orangered;
        }
        /* 유지 보수 측면상 자식 선택자보다 후손 선택자를 해야함 
         지인짜~~~ 자식 선택자 밖에 없을 경우 써야 함*/
        .wrap div{
            font-size: 1.5em;
            color: orangered; 
        }
    ```
- 정리하자면 후손 선택자를 하는게 유지 보수에 좋음!!!~~
- 후손의 후손의 후손을 넣으면 넣을 수록 우선 순위가 높음

### 9. 형제 선택자
- 인접 형제 선택자
- `+`는 형제를 의미
- `.orange + li { color : orangered;}` 형이 .orange 클래스를 가진 li 태그 
- 선택자는 어떠한 방법을 써서 선택만 할 수 있음
- `li + li { font-size: 24px}` 형이 li 태그를 가진 li 태그, 즉 첫번째 빼고 다 적용
- `tr + tr {}`테이블에 많이 응용됨
- 일반 형제 선택자
- `.red ~ li{}` 형들중에 .red 클래스를 가진 li 태그
- `+`는 직속 형, `~` 형들 중
- 선택자를 잘하면 웹 크롤링을 할 때 좋음

### 10. 그룹 선택자
- `h1, h2, h3, h4, h5, h6{}` h1~h6 태그 전부를 선택

### 11. 속성 선택자
- `input[type=password]{}` input태그의 type이 password를 선택
- `opacity: 0.8;` 투명도 80%
- `[disabled]` disabled 속성을 가지고 있는 것을 선택

### 12. 가상 선택자
- hover : 요소에 마우스를 올렸을 때 적용
- `.box:hover{}`
- active : 요소에 마우스를 누르고 있는 동안에 적용
- `.box:active{}`
- focus : 요소에 포커싱(탭, 입력창 클릭)
- `#common:focus{}`
- `transition : 6s` 6초에 걸쳐서 서서히 변함
- `outline : none;` 바깥선을 none으로 함
- `transform : rotate(720deg);` 2바퀴 회전
  