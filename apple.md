# 개발 사이트 
ex)[https://velog.io/@leitmotif/%EC%9B%B9-%EC%BB%A4%EB%A8%B8%EC%8A%A4-%EC%82%AC%EC%9D%B4%ED%8A%B8-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%9B%84%EA%B8%B0]

## 주제 예시
- [https://www.dataq.or.kr/www/main.do#none] 데이터 자격검정 
- velog 개발자 사이트
- 쇼핑몰
  
## 개발 예시
1) 회원가입
2) 로그인(비밀번호 찾기)
3) 개인정보 수정
4) 메인 페이지
5) 게시판
6) 로그아웃
7) 다크모드
8) 반응형 웹
9) 페이징 기능

## 역할 분담
### PPT 발표 및 제작
- PPT 제작 :
- PPT 제작2 : 
- PPT 발표 : 
- PPT 발표2 : 
- 시연 발표 :  
### 프로그램 기능 및 설계
- 팀장(1) :  
- 프론트(2) : 
- 백엔드(2) : 

---


## 개발 환경
- 노션(협업 내용 공유)
- 깃허브
- InteliJ, JAVA11, mariaDB, HTML, CSS, javascript, ajax ...
- 라이브러리
- Mybatis

## 초기 설정
- reset.css
## 프로젝트 구조설정
- com.spring.팀이름
    - .api
	- .controller
	- .dto
	- .entity
	- .repository
	- .service

- master 브랜치 -> 서비스
- develope 브랜치(최신화) -> 풀 땡기기
- 개발자1 브랜치
- 개발자2 브랜치
- 개발자3 브랜치
- 개발자4 브랜치 ex) featcher/board/write - 게시판 쓰기 기능 개발(유근) 
  - -> origin/develope 브랜치 풀 받은 다음 충돌 체크 및 기능 이상 없으면 push하기
  push 완료 후 해당 원격 브랜치 삭제
  - 새로운 기능 개발 시에는 origin/develop에서 branch 생성 후 개발 진행
 

---
## 주제 선정 및 기획 단계
- https://mklab-co.medium.com/%EC%9E%91%EC%84%B1%EB%B2%95-%ED%99%94%EB%A9%B4%EC%84%A4%EA%B3%84%EC%84%9C-wireframe-%EC%99%80-%EA%B8%B0%EB%8A%A5%EB%AA%85%EC%84%B8%EC%84%9C-functional-specification-bbcff0071ea2 명세서 작성하는 방법
1. 프로젝트 주제 선정
2. 요구사항 명세, 정의서 작성하기 API 명세서, 기능 명세서
   - https://know-one-by-one.tistory.com/114
3. ERD 그리기, 시나리오 작성하기
4. Wire Frame 그리기
5. 기획서(PPT) 초안 작성하기

---
## 개발 단계
- [ 백엔드 ]
1. 데이터베이스 모델링(공통 .sql 파일 작성) 
2. DTO, VO, SQL 구문 작성
3. DAO, Service, SQL 구문 작성
4. Controller 작성 (get, post, delete ) rest 방식으로
5. 테스트 코드 작성하기 (트랜잭션 처리)   

- [ 프론트엔드 ]
0. 화면설계서(wireframe), 스토리보드(StoryBoard)	https://yslab.kr/148
1. jsp, css, html 구조 설계하기
2. javascript 이벤트 처리하기

--- 
## 기록하기
- 버그사항
- 팀 노션을 통해 진행상황 등 기록하고 공유
### 코딩 규칙 정하기
- 패키지명 : 모두 소문자, 밑줄문자 사용하지 않음
- 클래스명 : 파스칼 표기법
- 인터페이스명 : 파스칼표기법, 명사, 형용사
- 메소드명 : 낙타표기법 lowerCamel
- 상수명 : 대문자명 표기법
- 비상수 필드명, 파라미터명, 로컬 변수명 : lowerCamelCase
- DTO, Entity: GuestDTO, replyEntity
- 저작권 문제 동의받기, 결제 기능 API 고려사항
