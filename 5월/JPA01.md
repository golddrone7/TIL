# JPA01

## 스프링 JPA
- Java Persistence Application
- 데이터를 영구적으로 저장한다
- 데이터베이스를 다루는 것
- Hibernate를 JPA라 불림
- ORM(Object-Relational Mapping)
- 페이징과 정렬 다 만들어짐
- spring boot는 3.버전은 시기상조임 게다가 jdk17이상에서 지원함
- Group : com.study
- Help.md -> readme.md
### yml 파일
- 문법이 다른 설정파일
```yml
server:
    port: 8181
```
- 계층적인 구조
- application.properties보다 많이 쓰임
- 들여쓰냐, 나열하냐의 차이
- 정답은 없음

- @Column에서 not null, length, 
### ddl-auto: create 중요!!
- drop을 한다음 다시 table을 create하는 거임
- 테스트할때만 함
- 개발할 때 데이터를 안날리고 싶다
- `ddl-auto: update`로 두고하면됨
- 컬럼명이 바뀔 경우 alter문이 나감
- 배포상황일 땐 none으로 설정함, 테이블을 미리 만들어야함


```java
package com.study.jpa.chap01_basic.repository;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.annotation.Rollback;
import org.springframework.transaction.annotation.Transactional;

import static org.junit.jupiter.api.Assertions.*;


@SpringBootTest
@Transactional
@Rollback(false) // 공부할 땐 false로 하고 실무에선 true로 함 
class ProductRepositoryTest {
    @Autowired
    ProductRepository productRepository;   
}
```

### 약어설정
- 인텔리제이 - 라이브템플릿에서 관리함
- tdd

## 랜덤 문자 pk
- pk는 랜덤문자로 하는게 맞음
- uuid

## jpa
- 경우의 수가 많음
- 이런게 있다 정도만 알 면 좋음
- QueryDSL이 더 편함
- 한국은 아직 mybatis를 주로 씀
- 복잡한 쿼리는 mybatis쓰고 간단한 쿼리는 jpa쓰는 경우도 있음
- 