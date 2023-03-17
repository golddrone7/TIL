# JavaScript
- ㅇ


## 형변환
- 타입을 변환
- 문자열 `+`는 연결 연산자
- 암묵적 형변환  `10+'20'` 의 결과는 `1020` 문자형으로 변환함
- `+'99'`는 숫자로 형변환을 암묵적으로 해줌
- js에서 0, '', null, undefined, NaN은 거짓으로 판단  (매우 중요)
### String, StringBuilder, StringBuffer
- 다량의 데이터가 들어 올 경우 String은 좋지 않음
- 컬렉션 자료구조가 List, HashMap인지 먼저 본 다음
- String 타입을 썼는지 확인 해준다. StringBuilder나 StringBuffer로 바꾸는 작업
- String 끼리 더하는 작업은 좋지 않음, 문제가 생길 여지가 있음

### 동적타이핑
- 타이핑을 명시하지 않음, 자바스크립트
- 타입을 추론함(성능이 좋지 않음)
- 해결하기 위해 타입스크립트 등장
### 정적타이핑
- 자바에서 사용
- 타입을 명시함

### 논리 연산
- 첫번째 truthy를 찾는 OR연산자
- 첫번째 falsy를 찾는 AND연산자
```javascript
    <h1>안녕하세요 우리 홈페이지에 오신걸 환영합니다.</h1>
    isLogin() && <h2>xxx님 안녕하세요!</h2>
    로그인을 하면 h2태그가 나오지만
    로그인을 하지 않으면 isLogin()만 호출함 


    쿠폰 당첨되면 쿠폰 보내줌 
    쿠폰당첨플래그 && sendCoupon()

    나의 아티클이면 수정버튼이 보임 
    isMineArticle() && <button>수정</button>
    리액트에서 많이 사용함
```

## 배열기초
- ㅇ
- ㅇ
- ㅇ
- ㅇ
- ㅇ
- ㅇ
- 