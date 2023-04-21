# web06

## 인텔리제이 단축키
- ctrl+alt+m 메서드 추출
- ctrl+alt+v 변수 추출
- ctrl+alt+p 경로
- ctrl+alt+n 리펙터링
- 
## 서버에서 데이터 받기
- 성적정보를 dot
- dto를 재활용하면 안됨
- 설계를 잘해야함, 안그러면 꼬임
- 백엔드 작업을 하고 프론트 엔드에 필요한 정보만 보내주자
- EntityRequestDTO     (요청 DTO)
- EntityResponseDTO    (응답 DTO)
- Score

### Service를 만드는 이유
- 단일책임원칙(SRP)를 잘 지키기 위해
- 하나의 클래스는 많은 역할을 만들면 안됨.
- 하나하나 씩 개선하면서 의존관계를 끊어야 함
- 
## 3 Tier Architecture

### controller (홀 직원)
- 주어진 요청을 받고 서비스로 전달하는 역할
- 처리 후 결과를 바탕으로 jsp 파일로 전달하는 역할
- 야 요청 똑바로 받아! 주문 똑바로 받아
1. URL 맵핑 잘하고 파라미터를 잘 세팅함(DTO)
2. 그 요청을 처리할 서비스를 찾아야함 (정확하게 연결)
3. 화면 응답처리(모델에 잘 담고 redirect...)

### Service
- 컨트롤러와 레파지토리 사이 비즈니스 로직 처리
- 등록할 때 클라이언트가 비밀번호를 넣는데 데이터베이스를 그냥 넣진 않음, 암호화처리 작업...
- 목록 요청할 때도 중요한 정보를 변환하는 작업을 해야함(마스킹)
1. 비즈니스 로직을 수행하는 역할
2. 그 결과를 다시 Controller에 전달
3. 여러 개의 Repository를 사용하여 데이터를 처리

### Repository
- DAO(디에오)
- 데이터 저자오
- 저장소 데이터와 관련된 것들을 처리

## MSI식 
- 하나의 앱을 만들 때 기본의 패키지
- controller(api)
- dto
- entity(vo, model)
- repository(dao)
- service

## 팁

- 게시판 조회수 올라가는 기능 같은 경우는 service단에서 만드는게 좋음
- 