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

ㅇ