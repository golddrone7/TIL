# JavaScript
- 나만의 길을 걷기
- 대신 꾸준히 하기, 놔버리면 안됨
- 책을 하나하나 쌓음으로써 문명이 발전해감
- 사용자의 편의성을 생각해서 프로그래밍 하기
- 
## 제어문

### 중첩반복문
```javascript
money : for (var i=0; i<3; i++){
    for(var j=0; j<2; j++){
        if(i ===j)
            break money;
        console.log(`[ ${i}, ${j}]`);
    }
}
console.log('===========================');
```

- 앵그리버드는 자바 스크립트로 만듬
- 