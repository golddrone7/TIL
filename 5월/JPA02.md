# JPA02

## JPA Pagination, Sorting
- DB 무리가 가기때문에 Pagination 처리를 함

### JPA TEST
```java
// 만약에 서비스클래스를 사용한다면 해당 클래스에 붙일 것!
@Transactional // JPA는 I, U, D시에 반드시 트랜잭션 처리가 필수
@Rollback
@SpringBootTest
```

### Pagination

```java
@Test
    @DisplayName("기본 페이징 테스트")
    void testBasicPagination(){
        //given
        int pageNo = 1;
        int amount = 10;

        //페이지 정보 생성
        //페이지번호가 zero-based
        Pageable page = PageRequest.of(pageNo - 1, amount);

        //when
        Page<Student> students = studentPageRepository.findAll(page);
        List<Student> studentList = students.getContent();
        //then
        System.out.println("\n\n\n");
        studentList.forEach(System.out::println);
        System.out.println("\n\n\n");
    }

```
### "도시시99" > "도시시147"

## DB, 객체 패러다임
- 객체는 둘다 update해야함(양방향)
- DB는 한곳만 update하면됨
- 버전 확인, 반대편처리...




### S1
- 엔터티 설계
- 메뉴 구성도
### S2
- DB 설계
- 와이어프레임
### S3
- 프론트 설계
### S4
- 백엔드 설계, PPT
### S5
- 버그 테스트


## 
### 일반 페이지
- 마이페이지
- 수강페이지
- 상담페이지(실시간 채팅||채팅||쪽지)
- 출석페이지(QR, 비콘, 와이파이)
- 
### 관리자 페이지
- 회원 관리
- 강의/과목 관리
- 수강 관리
- 출결 관리
- 성적 관리
- 결제 관리
- 시스템 관리
- 보고서 및 통계 기능
- 일정 기능
- 알림 기능








