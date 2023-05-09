# CSR03

- <a>기능을 막는다. 비동기 ajax로 처리해야함 preventdefault
- 부모한테 삭제기능을 걸어야 자식한테도 모두 걸림, 이벤트 버블링
- 부트스트랩 모달창은 자바스크립트 cdn하고 부트스트랩 cdn 2가지가 필요함

- 아이디 중복검사 0이면 가입 가능 1이면 가입 불가능 (PK)
- DB를 만들면 ENTITY를 만들자
- 인터페이스를 구현해서 어떤 기능을 만들것인지 정의
- Mapper.xml에서 설정파일을 한 후
- mybatis-config에서 mapper와 typealias를 설정하자
## Mapper의 values #{}은 getter를 만들어야 생성됨
```xml
<insert id="save">
        INSERT INTO tbl_member
            (account, password, name, email)
        values (#{account}, #{password}, #{name}, #{email})
    </insert>
```