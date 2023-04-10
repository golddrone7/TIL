# Java
- 자바 베이스 모듈

## 자바 베이스 모듈
- Application Programming Interface
- 게시판 API
- 제목, 내용, 작성자, 조회수, 등록, 수정, 추천, 비추천
- 조회수 상승, 즐겨찾기...
- 회원 API
- 회원 계정명, 비번, 등록, 마이페이지 수정, 변경, 찾기...
- API 개발자가 된다는 것은 백엔드개발자
### API
- java.lang 패키지는 import 생략이 가능함
- toString()은 재정의가 필수임

## lombok 라이브러리
- 필드만 넣고 어노테이션으로 생성자를 만듬

### equals, hashCode
- 오버라이딩 같이 하기


### System 클래스
- 운영체제의 정보를 쉽게 얻어 낼 수 없어서 만들어짐
#### gc
- 드래곤플라이트 2010년 당시 핸드폰이 128MB 램이었음
- 그 당시는 고사양 게임을 못만듬
- Angry Bird, 애니팡...
- 안드로이드는 자바로 만들어야됨
- 최적화 문제있어서 gc를 남발한 적이 있음
- 조금 빨리 움직이지만 의도대로 빠르게 움직이진 않음

### String 클래스
- length()
- charAt()
- subString()
- toUpperCase()
- toLowerCase()
- split()

### StringBuffer, StringBuilder
- `String s = "hello";`
- `s = "hello world";`
- 배열은 방크기를 스스로 못늘림
- 배열 복사를 한 다음 복사를 하기 때문에 속도가 느림
- 메모리는 여전히 "hello" 데이터가 있음
- s가 만약 1억번의 데이터의 변경이 일어날 경우 메모리 부하가 날 수 있음
- 개선하기 위해 StringBuffer, StringBuilder임
- 요즘 말이 많음
- String을 써서 큰 병목이 일어나지 않아서 그냥 String을 써라가 요즘 추세
#### 알고리즘
- 문제를 위한 문제
- StringBuilder를 써야지 알고리즘 시간 제한에 좋음
- 시간 초과에 대비하자

### Wrapper 클래스
- Integer 
- 오토박싱 `Integer a = 10;`
- `int a = 10;` 서로 변환이 가능
- Integer을 쓰면 정수 관련 메서드들을 쓸 수 있음
- 다른 밸류들을 많이 바꿀 수 있음
### 클래스 설계를 하게 되면 어떤 사람은 여기에 long을 소문자로 쓰고 대문자로 쓰는 사람도 있음 (중요)
- 기본값의 차이
- `int price;`는 기본값이 0이지만
- `Integer price;`는 기본값이 null임

### 날짜
- @Deprecated 쓰지말란 소리
- 자바에서 쓰지말라고 하면 쓰지않는 것이 바람직
- `LocalDateTime` 을 쓰자

## 파일 입출력이 중요한 이유
- 파일 올리거나 내리거나, 업로드 다운로드
- 썸네일
- 세이브 파일
- 프로그램이 기준
- 세이브는 HDD로 내보냄(출력)
- load는 HDD 정보를 가지고 옴(입력)
- 모든 데이터들을 스트림으로 보낼 수 있음
- 출력 스트림, 입력 스트림
- 바이트 기반 스트림은 1바이트씩 자름(사진, 영상, 파일)
- 문자 기반 스트림은 2바이트씩 자름(한글, 텍스트)

### try-with-resource
- auto closing함
- try(여기에 작성) 안에 객체를 생성함
- 스프링은 인터페이스를 작성하면 끝남

### 예전 세이브 파일
- memberId=1, email=aaa@bbb.com, password=1234, memberName=대길이
- memberId=1, email=bbb@bbb.com, password=1234, memberName=중길이
- memberId=1, email=ccc@bbb.com, password=1234, memberName=소길이
1. \n이 나올떄까지 읽음
2. ,를 기준으로 문자열을 짜름
3. =을 기준을 문자열 짜름
4. new Member()
5. set ...
6. Member[] memberList;에 쌓음.

- 알고리즘은 Scanner보다 BufferedReader를 사용하는 것이 시간 효율적
- 캐리지 리턴 \r 왼쪽으로 커서 이동


### 객체 직렬화 
- 직렬화 시리얼넘버를 지정해야함
- 객체는 메모리는 바이트형태로 이루어짐
- Snack 객체안은 byte로 되어있음
- 배열처럼 일렬로 세워야함
- 객체는 덩어리라서 한줄로 세워야함(직렬화)
- List는 직렬화가 되어있지만 Snack객체는 직렬화가 되어있지 않음
- 
