# CSR10

## 카카오 로그인 
- 나머지 기능을 알아서 만들어볼 것
- 카카오 뿐만 아니라 네이버, 구글 로그인도 구현해보기
- ㅇㅇㅇ
- 어떤 API든 문서보고 따라하면 됌
- 회원가입의 통합화
- favicon 넣어보기
- TITLE 
- 로고만들기
- 누끼따기


## 궁금증

### Q
- application.properties 파일은 github에 올리면 안되나
- 그러면 협업시에 설정 파일은 어떻게 공유하는가
### A
- 협업 시에는 각 개발자가 로컬 환경에서 자체적으로 application.properties 파일을 생성하고 관리하는 것이 일반적입니다. 이렇게 하면 개인별로 다른 설정을 사용할 수 있으며, 보안과 개인 정보의 보호를 유지할 수 있습니다.

- 공통된 설정이 필요한 경우, 일반적인 방법은 "샘플" 또는 "기본" 설정 파일을 저장소에 추가하는 것입니다. 이 파일에는 기본 설정 값이 포함되어 있지만, 실제 개인 정보는 비워져 있습니다. 개발 팀의 구성원은 이 샘플 파일을 참조하여 자신의 로컬 환경에서 실제 설정 값을 추가하고 저장할 수 있습니다.

- 일부 개발 팀은 외부 구성 관리 도구를 사용하여 설정 값을 관리하기도 합니다. 이러한 도구는 개별 설정 파일 대신 중앙화된 구성 저장소에서 구성 값을 가져오는 방식으로 작동할 수 있습니다. 예를 들어, Spring Cloud Config나 HashiCorp의 Vault와 같은 도구를 사용하여 구성을 중앙에서 관리하고 애플리케이션에 제공할 수 있습니다.

- 어떤 방법을 선택하든, 중요한 점은 개인 정보와 보안 설정을 공개 저장소에 업로드하지 않는 것입니다. 개인 정보는 로컬 환경이나 안전한 중앙 구성 관리 도구를 통해 관리되어야 합니다.

## 서버와 서버에 통신하는 방법
- ㅇㅇ
- 