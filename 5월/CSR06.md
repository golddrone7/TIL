# CSR06

## 인증 vs 인가, 인터셉터

### 인증(Authentication)
- 인증은 사용자의 신원을 확인하는 과정
- 아이디 인증, 지문 인증, 얼굴 인식 인증


### 인가 (Authorization)
- 사용자가 특정 리소스에 대한 권한을 가지고 있는지 확인하는 과정
- 사용자의 역할(Role)이나 권한(Permission)을 기반으로 관리한다.


### 인터셉터
- 요청을 가로챔, 로그인 인증한 회원만 들어올 수 있음



```java
@Override
    public void addInterceptors(InterceptorRegistry registry) {
        // 게시판 인터셉터 설정
        registry.addInterceptor(boardInterceptor)
                .addPathPatterns("/board/*") // 어떤 경로에서 인터셉터를 실행할 것인가
                .excludePathPatterns("/board/list", "/board/detail") // 인터셉터를 실행하지 않을 경로
        ;
    }   
```

- 인터셉터 처리를 안하면 주소창으로 들어올 수 있음
- 즉 프론트에서 안보이게 처리하고 주소창도 인터셉터 처리를 하기
- 회원제 게시판을 가기 위해 DB에서 연관관계를 추가해줘야함 
- list.jsp, x버튼을 조건부 렌더링이 되어야함, 그 조거능ㄴ 
- 로그인하면 회원가입, 로그인창으로 가지 못하게 막기