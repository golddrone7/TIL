# JavaScript

## 콜백 복습
- 동작을 파라미터화
  
### 클로저란
- 자바스크립트의 특수한 기능
- `const calculator = (n1, n2) => ()=> n1 + n2;` 느낌
- 효율성이 올라간다면 쓰자
- 가독성이 안좋아지면 쓰지말자
- 함수를 줄이는 방식임
- 활용 : 카운터 기능, 먼가 누를때마다 숫자가 하나씩 올라감
- 도구를 주고 지역변수를 카운팅 증가함
- 전역 변수 남발을 막기 위해 사용함
- 상태 유지가 필요한 변수들을 사용할 때 클로저를 사용함
- 클로저 함수 라이브러리들이 많음

### Stateful 과 Stateless
- 상태 유지를 하지 않으면 로그인했는지 여부를 모름
- 쿠키, 세션, 캐시, 토큰을 통해 해결

### 즉시 실행 함수 
- 정의와 동시에 호출, 1회용이라 이름이 없음
- 1회용 함수
- `(function(n1, n2){})();`
- 함수를 소괄호로 한번 묶고 (), 바로 실행하자 ()
```javascript
const increase = (()=> {
    let count = 0; // 지역 변수
    return () => ++count;
})();
```
### 코드 리팩토링
- 코드가 워낙 길어서 줄이는 작업
- 리펙터링, 클린코드

## 객체 구조분해 할당
- 객체 안전 복사 : 스프레드
- 복사하면서 추가 프로퍼티 만들래!
- 프로퍼티가 겹칠 경우 수정이 됨,,,,
- 기존의 데이터를 수정하고 싶으면 복사하면서 수정하자!,, 리엑트 기법
```javascript
const copyEmp = {
    ...emp,
    address : '서울시',
    hobbies : ['놀고먹기', '낮잠'],
    empName : '망둥어'
};

console.log(copyEmp)
```
### 주의할점
- gameData 디스트럭처링
- 디스트럭처링은 사본에 복사하는거라 변경해도 원본에 적용되지 않음
- 읽기전용  사본 데이터로
- 쓰기포함은 원본 데이터로


## DOM 기초
- DOM (Document Object Model)
- 문서객체모델
```javascript
box = {
    tagName : 'div',
    attribues : {
        id : 'box'
    },
    children: [input,],
    //parentNode : document.body
}

input = {
    tagName: 'input', 
    attribues: {
        id : 'abc',
        classList : ['zzz', 'xxx', 'vvv'],
        type : 'text'
    },
    parentNode : box
};
```
- document, html, body는 모든 사이트가 같음
- 그 아래는 커스텀된 부분이라 방법에 대해 알아야 함
- 트리 탐색 DFS, BFS
- 어떤 함수들이 탐색을 해줌
- 계층적 구조
- `const $banana`는 태그라는 관례가 있음

### querySelector 
- class가 중복일 경우 첫번째 요소 선택
- 클래스가 틀리거나 문법이 틀릴경우 에러
- 클래스는 .을 붙이고 아이디는 #을 붙임
```javascript
const $grape = document.querySelector('#fruits li:nth-child(3)');
```
- 한가지 요소만 가지고옴
- 전체 다 가지고 올려면??
- `querySelectorAll`를 쓰자
- 유사배열 NodeList 주의하기 Pop push slice 배열 함수 안됨!
- elements.pop(elements);
- console.log(elements);
- 유사배열에서 찐배열로 바꿔서 사용하자
- 