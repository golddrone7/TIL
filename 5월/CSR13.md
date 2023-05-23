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


## State
- 상태변수값 유지
- 클로저 개념


## 연계기업
- 정해지면 기업에서 제시하는 프로젝트가 있음
- 자유주제로 못함
- 연계기업이 괜찮으면 하는게 좋고
- 아니면 자율 프로젝트하는게 좋음
- 기술 스팩을 미리 다 정해짐
- 회사를 타겟팅하고 요구하는 스팩을 파이널 프로젝트로 진행하는 것이 좋음

## 채용트랜드
- 코테 비중이 높았다가 낮아짐
- GTP땜에 안믿음
- 회사에 불러서 미니 프로젝트를 시킴(3일 과제)
- 실전형 프로젝트
- 6월 7일부터 시작하지 않을까?
- 그런데 2일이 금요일인데 첫번째 기업이 설명을 함
- 