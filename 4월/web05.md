# web05

## CRUD 점수 관리 시스템

## 0. 개발 원칙
- MVC 파트는 패턴대로 쓰면 됨
- ~~~Repository
- ~~~Controller
- ~~~View
- AppConfig.java
- Interface 설계(다형성)
- SOLID 원칙 준수
- 클래스다이어그램
- 테스트 주도 개발(단위테스트 작성)


## 1. 패키지 설계
- 패키지 이름 : entity, controller, repository, dto
  

## 2. URL 설계
```java
 # 요청 URL (실무가면 나옴)
    1. 학생 성적정보 등록화면을 보여주고 및 성적정보 목록조회 처리
    - /score/list : GET
    
    2. 성적 정보 등록 처리 요청
    - /score/register : POST
    
    3. 성적정보 삭제 요청
    - /score/remove : POST
    
    4. 성적정보 상세 조회 요청
    - /score/detail : GET
```

### 2-1. 잘 넘어가는지 테스트 해보기
- `System.out.println()` 로그 찍어보기

### 2-2. 틀 잡기
```java
// 성적등록화면 띄우기 + 정보목록조회
    @GetMapping("/list")
    public String list(){
        System.out.println("/score/list : GET!");
        return "";
    }
```
### 2-3. 요청이 잘 들어오는지 테스트하기
- 웹 환경에서 주소로 테스트해보기
- [http://localhost:8181/score/list] GET 404, 콘솔 내용 표시
- [http://localhost:8181/score/remove] POST 405, 콘솔 거부
- 제대로 테스트하면 다른 도구가 있음

### 2-4. CRUD를 하기 위해선 메모리, 데이터베이스가 필요
- 저장소 개념 관리를 해줬으면 좋겠음
- public interface ScoreRepository 생성
- 역할 명세 (추상화) :
- 성적 정보를 잘 저장하고 추가하고 조회하고 수정해야 한다.
- findAll(), save(), deleteBy()와 같이 역할에 맡는 직관적인 용어를 사용 메서드
- 기능 명세
```java
  // 성적 정보 전체 목록 조회
    List<Score> findAll();
    // 성적 정보 등록
    boolean save(Score score);
    // 성적 정보 한개 삭제
    boolean deleteByStuNum(int stuNum);
    // 성적 정보 개별 조회
    Score findByStuNum(int stuNum);
```
- 인터페이스화 시키면 협업하는데 지장이 없음
- Controller화하면 있다 치고 작성할 수 있음
- 마치 있는 것처럼 작동할 수 있음

### 2-5 구현체 작성하기
- 구현체가 하나라면 ScoreRepositoryImpl ~~~Impl을 작성
- 구현체가 여러개라면 정확히 작성하자
- ScoreMemoryRepository
- ~~~Repository
- 미리 데이터를 넣어둠

### 2-6 잘 작동하는지 테스트하기
- Junit
- 테스트 시나리오 작성
- 단언(Assertion) 기법
- 우린 findAll()을 할 때 3개가 나와야 함!!!!!!!!
- given-when-then 패턴 유명한 단위테스트 패턴
- given : 테스트를 위해 주어질 데이터 (ex: parameter)
- when : 테스트 실제 상황
- then : 테스트 결과 확인
- 나는 스코어리스트의 사이즈가 3인 것이 참이라고 단언하다.
- `assertTrue(scoreList.size() == 3);`
- assertTrue보다 assertEquals가 명확함
- 실제 검증값을 볼 수 있기 때문
- QA는 하루종일 테스트만 함
- 테스트 하는 시간을 아까워하지말자, 해당 메서드를 믿고 쓸 수 있음
- junit5는 default 제한으로 만들어야함
- 모든 상황에서의 테스트를 해주자(있는 데이터 검증, 없는 데이터 검증)

### 2-7 view, jsp 파일 작성, 스프링 어노테이션 적용

### Redirect
- 재요청
- 삭제하고 재요청
- 등록하고 재요청
- 
### Forward


### 다음주
- 오전 DB
- 오후 스프링 + DB 연결 작업
- 