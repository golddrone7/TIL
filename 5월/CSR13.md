# CSR13

## 클론할때 주의사항

- TlJIVGZoR3hzT0swUHZnSm5NamR5Zz09
- npm start가 안됨
- npm install을 한번 적어줘야 함
  

## Props
- 상위 컴포넌트가 하위 컴포넌트에 데이터 전달 가능
- 인텔리제이는 webstorm으로 개발함(프론트)
- 자바스크립트의 모든 타입을 보낼 수 있음
- {} 정수, 불린 다 가능
```jsx
import React from 'react'

const FoodItem = ({foodId: id, foodName: fName, price}) => {

    //console.log('props: ', props);
  return (
    <li id={id}>{fName} ({price}원)</li>
  )
}

export default FoodItem
```

### 태그를 보낼때 사용
```jsx
    <SayHello>
        <a href='https://www.naver.com'>네이버 링크</a>
      </SayHello>
      <SayHello>
        <a href='https://www.google.com'>구글 링크</a>
      </SayHello>
```