# REACT2

## TODO app 2일차
- 폼은 새로고침, 서브밋 기능을 빼줘야함
- 다른 곳에 갈 곳이 없음 SPA이기 때문에, 하나의 웹 페이지만 존재함
- 리액트는 기본적으로 화면전환이 이뤄지면 안됨 SPA이기 때문임
- `e.preventDefault();` 
- 폼은 활용하지만, submit 기능을 빼줘야함 

### 콘솔 로그 빨간 원인
- 반복적으로 컴포넌트를 렌더링이 되면 키를 주자
- 절대 겹치지 않는 아이디 값을 하나씩 줌
- `todoList.map(todo => <TodoItem key={todo.id} item={todo} />)` 
- 성능 최적화 문제

### 리액트스러운 코드
- 페이로드 만들어서 객체를 올려보내면 됨 
- but 바닐라 스러운 코드임
- 실제로 구현이 어려우면 querySelector 씀
- 리액트는 input에 state를 상태값을 넘겨줌

### 데이터 전달
- 상위 컴포넌트에 하위 컴포넌트로 데이터를 전달하는 건 props로 쉬움
- 반대의 상황(하위 -> 상위) TodoTemplate 쪽으로 데이터를 보냄
- 콜백을 사용하자!!!!!!!!!!!!!!!!!!!!!
- 쫌 어려움
- TodoInput 한테 콜백함수를 props로 전달함
- TodoInput에서 함수를 불러서 콜백으로 전달함

### 리액트의 상태값
- 리액트의 상태값은 무조건 set으로만 사용하자!!
- 이 룰만 기억하자
- state
```java
// 리액트의 상태변수는 무조건 setter를 통해서만 
// 상태값을 변경해야 렌더링에 적용된다.
// 다만 상태변수가 불변성(immutable)을 가지기 때문에
// 기존의 상태에서 변경이 불가능하고
// 새로운 상태를 만들어서 변경해야 한다.
```
- 리액트는 객체를 불변성으로 가지기 때문에 새로운 배열을 만들어서 거기에 5번째 데이터를 붙이고 갈아껴줘야함
- 성능의 문제가 있을 수도 있지만 리액트가 다 알아서 관리를 해줌
- 리액트는 상태값으로 관리해야 렌더링을 하면 값이 보임
- 상태값으로 관리를 하면 불변성 제약 조건이 있음
- push, pop을 사용하지 못해서 setter를 통해서 이뤄짐
- 새로운 배열로 교체해줌
- `setTodos([...todos, newTodo]);`
- `setTodos(todos.concat([newTodo]))`

### 웹디 기능사
- 사이트 디자인을 실제로 함
- 요구사항 표가 나옴(와이어 프레임)
- 리액트 개발자가 실제로 안나옴
- 백엔드하다가 가는 경우가 많음
- 백엔드 API을 기똥차게 만듦??!?!@_@_@_@_@

### 리액트를 배운다면
- 모바일을 따로 배울 필요 없음
- 네이티브 App
- 앱개발자를 따로 썼어야 함
- 웹 프론트, 모바일, API 개발자로 역할 분담했음
- 리액트 네이티브 app (ios, android)
- 웹 UI, 모바일 UI
- RN, 플러터
- 실무하면 공부하기 힘듬

## 향후 일정
- 화~금 Spring JPA
- 6/5 나와야함
- 6/5~ SQLD
- 5/31 기업 프로젝트 설명회
- 일찍끝나면 JPA 이어감
- 리액트랑 같이 JPA랑 붙임
- 어떻게 결합되는가, 연계되는가 
- 2주 가량은 파이널 진행되고 있는 가량에 AWS 배포 운영에 대한 이야기
- 프로젝트 1차 베타버전이 나와야함
### 회사고를 때 
- `더존비즈온`
- 회사를 고를때 자사 서비스(솔루션)이 있는지를 확실하기 보기
- 견적/구매
- 파견 회사인지 
- `LG CNS, SK C&C`
- 1차, 2차, 3차 하청
- 자사 솔루션이 있는 SI가 best
- 스타트업은 처음부터 다 해야함
- 