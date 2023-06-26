# AWS07

## 배포하는 법
- EC2 접근 가능한 계정
- 인스턴스 시작
  - 이름 : 본인 프로젝트 이름
  - `hahahoho-backend-api-server`
  - 역할을 명시하는 것이 좋음
  - Amazon Linux aws로 하기
  - 리눅스가 가벼움, 보통 리눅스로 배포함
  - 프리티어 사용 가능
  - 키페어는 만들고 보관하는 것이 좋음
  - 네트워크 설정에서 보안 그룹 선택, 모두 체크하면 다 허용해줌 
  - `SSH 트래픽, HTTPS 트래픽, HTTP 트래픽 허용`
  - 스토리지 구성은 용량을 의미
  - On-demand로 사용하면 됨
  - Auto-Scailing, LoadBalancing은 개념만 알자 돈나감
  - 실행중인 인스턴스를 하나 만듬
  - 어떤 방법이든 원격으로 인스턴스에 접속하면 됨 `putty` 

### 탄력적 IP 주의사항
  - 인스턴스 IP가 고정이면 좋음(탄력 아이피를 설정하기)
  - 탄력적 IP에서 하나 할당 받아서 EC2가 있는 region ap-northtest-2를 선택하고 할당받기
  - 다시한번 말씀드자면 할당받고 인스턴스 연결을 안하면 `과금`됨
  - ## 할당받고 탄력적 IP 주소 연결을 무조건 해주자
  - 리소스 유형은 인스턴스, 지금 실행중인 인스턴스를 선택한다음에 연결하기
  - 종료하면 탄력적 IP 주소를 릴리스하자!! 꼭 기억해야함
  - EC2 정보에서 퍼블릭 Ipv4 주소와 탄력적 IP주소가 일치하는지 확인하기

## 원격접속
  - 호스트네임에 ec2-user@3.39.84.104     {탄력적 아이피 주소적기}
  - Auth -> credintial 에서 ec2-practice-key.ppk 설정하기
  - accept까지 1차적으로 준비하기

## 배포할 프로젝트를 인텔리제이로 열어주기
- aws에 jdk 설치하기
- 배포할 프로젝트와 호환성을 맞춰야함
- 인텔리제이 : 파일 -> 프로젝트 구조, SDK 확인하기
- 리눅스는 명령어 기반 설치
### 리눅스
- sudo yum install java-11-amazon-corretto.x86_64 -y    {리눅스에 jdk 설치하기}
- java --version, 버전이 설치되어있는지 확인하기
- sudo timedatectl set-timezon 'Asia/Seoul'        , 싱글쿼터(따옴표) 조심하기
- RDS 들어가기
- 10.6.9, 프리티어, db 식별자 이름 지정, 루트 계정 생성, 
- 스토리지 자동 조정 활성화 끄기!! , 퍼블릭 액세스 예, 보안 그룹 기존 항목 선택
- my-api-server-sg, DB 파라미터 그룹은 rds-mariadb-pg 
- 데이터베이스 생성, 보안그룹 인바운드 규칙 편집 확인하기
- SSH, HTTPS, HTTP 
- 인바운드 규칙 추가
- [포트범위] 3306, [소스] ec2 탄력 아이피 또는 보안그룹 넣기, 0.0.0.0/0
- [유형] MYSQL/AURORA
- ### 파라미터 그룹
- 편집, timezon 설정을 asia로 바꿔주고
- char, UTF-8, collation general  
- DB에서 파라미터 연동, 수정 누르고 추가 구성에 생성한 그룹 넣어주고
- 계속하고 수정 예약을 `즉시 적용`해야함  (바로 확인됨)
- DB 엔드포인트, db의 url을 복사하고 ec2에 `sudo yum install mysql -y` 설치하기
- `mysql -u root -p -h`
- MariaDB [(none)]> show databases;
- MariaDB [(none)]> use prj
- MariaDB [(none)]> show tables;
- MariaDB [(none)]> exit
- [ec2-user@ip-172-31-34-251 ~]$ `sudo yum install git`
- [ec2-user@ip-172-31-34-251 ~]$ `git`
### 인텔리제이
- application.yml
- .gitignore 에서 application.yml 설정하기ㅍ
- 실무에선 application-template.yml github에 올림, 키만 따다닥 지움
- template을 이름 변경해서 쓰임
- application.yml은 로컬에서만 쓰기!! 중요함
- build.gradle 은 확인할게 test임
```java
 tasks.namd('test){
   exclude '**/*' // 빌드시 전체 테스트 생략
   }
```
- 단위 테스트의 핵심은 실제 코드에 영향을 주면안됨
- 이 테스트를 돌리면서 실제 로직이 변경되거나 데이터베이스 변동이 되면 안된다.
- assert로만 테스트하고 끝나면 롤백을 해야함
- 문제가 생길 수 있는 여지가 있음, bulk insert
- 빌드를 하게 되면 테스트 실행 케이스를 다 실행하게됨
- 편의상 개발 할 때 문제가 생길 여지가 있어서 생략함, 원랜 해야함
- 톰캣에 올려서 얘를 배포를 해도 되는지 테스트를 하기
- `localhost:8888/ynfinal/employees`
- 서버가 죽었나 살았나 판단하는 컨트롤러, 로드 밸런스가 확인함
- 토큰을 쓰고 있으면 health-check는 시큐리티 해제를 해야함
- `antMatchers~~~ .permitAll`
```java
@RestController
@Slf4j
public class HealthCheckController{

    @GetMapping("/health-check)
   public ResponseEntity<?> healthCheck(){
    log.info("server is running.. I'm healthy!");
    return ResponseEntity.ok().body("It's OK!");
   } 
}
```
- 이 프로젝트를 깃허브에 업로드함

### 2차시
- [ec2-user@ip-172-31-34-251 ~]$ pwd
- [ec2-user@ip-172-31-34-251 ~]$ cd/
- [ec2-user@ip-172-31-34-251 ~]$ ls/
- [ec2-user@ip-172-31-34-251 ~]$ cd usr
- [ec2-user@ip-172-31-34-251 ~]$ cd local
- [ec2-user@ip-172-31-34-251 ~]$ pwd
- [ec2-user@ip-172-31-34-251 ~]$ mkdir project
- [ec2-user@ip-172-31-34-251 ~]$ sudo su                루트계정
- [ec2-user@ip-172-31-34-251 ~]# pwd
- [ec2-user@ip-172-31-34-251 ~]# mkdir project
- [ec2-user@ip-172-31-34-251 ~]# ls
- [ec2-user@ip-172-31-34-251 ~]# cd project/
- [ec2-user@ip-172-31-34-251 ~]# git clone [저장소 원격주소]
- [ec2-user@ip-172-31-34-251 ~]# ls
- [ec2-user@ip-172-31-34-251 ~]# cd todo-api202306/
- [ec2-user@ip-172-31-34-251 ~]# cd src/main/
- [ec2-user@ip-172-31-34-251 ~]# ls
- [ec2-user@ip-172-31-34-251 ~]# mkdir resources
- [ec2-user@ip-172-31-34-251 ~]# ls
- [ec2-user@ip-172-31-34-251 ~]# cd resources
- [ec2-user@ip-172-31-34-251 ~]# vi application.yml
- i 누르고 application.yml파일복사하고 붙여넣음,
-  ddl-auto: update 
-  RDS endpoint 설정하기 : url : jdbc:mariadb://teamprj-database.cbcszxd0fody.ap-north-2.rds.amazonaws.com:3306/prj 
-  port : 80
-  logging.level:
   -  org.hibernate.SQL: info
- esc눌러서 insert모드 빠져나오기
- vi툴 사용이 어려우면 로컬에서 바꾸고 붙여넣어도됨
- :wq
- tail -200p application.yml
- [ec2-user@ip-172-31-34-251 ~]# cd /usr/local/project/todo-api202306/
- [ec2-user@ip-172-31-34-251 ~]# ls
- gradle의 Tasks/build/build
- 수동으로 터미널에서 build를 해야함
- [ec2-user@ip-172-31-34-251 ~]# ./gradlew build
- bash: ./gradlew: Permission denied, 권한 거부당함
- [ec2-user@ip-172-31-34-251 ~]# ls -l
- -rw-r--r--, -는 폴더 x권한을 줘야함, 
- drwxr-xr-x. 디렉토리
- 권한 읽기 4점, 쓰기 2점, 실행 1점
- [ec2-user@ip-172-31-34-251 ~]# chmod 777 `모든 관리자, 그룹, 사용자에게 읽기 쓰기 실행 권한을 다준다는 의미`
  - [ec2-user@ip-172-31-34-251 ~]# chmod 741 
- [ec2-user@ip-172-31-34-251 ~]# ls -l
- [ec2-user@ip-172-31-34-251 ~]# ./gradlew build
- 첫 빌드는 라이브러리를 받아야하기 때문에 느림
- [ec2-user@ip-172-31-34-251 ~]# cd build/
- [ec2-user@ip-172-31-34-251 ~]# ls
- [ec2-user@ip-172-31-34-251 ~]# java -jar todo-0.0.1 SNAPSHOT
- [ec2-user@ip-172-31-34-251 ~]# java -jar build todo-0.0.1
- 백그라운드 실행
- [ec2-user@ip-172-31-34-251 ~]# sudo su
- [ec2-user@ip-172-31-34-251 ~]# cd /usr/local/project/todo-api202306/
- [ec2-user@ip-172-31-34-251 ~]# nohup java -jar build/libs/todo-0.0.01-SNAPSHOT.jar &
- [ec2-user@ip-172-31-34-251 ~]# tail -200 nohup.out
- [ec2-user@ip-172-31-34-251 ~]# tail -200 
- post man에 http://탄력아이피주소/api/auth
- 