# JPA03

## N+1 문제 및 fetch join
- 1번의 select인데 부서별로 나옴(10개라면 11개 쿼리 조회)
- join을 쓰면 됨
- fetch join으로 써야함
- jpql을 써야함


## 테이블
- 테이블은 직접 만들자
- yml을 ddl-auto:none 설정하기