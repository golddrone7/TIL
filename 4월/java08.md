# Java

## 다형성
- B 객체의 타입은 부모의 타입을 사용할 수 있음
- 자식의 객체는 부모 타입을 사용할 수 있음
- 타입 캐스팅에 대한 얘기
- 자식객체는 상속관계에 있는 상위타입을 사용할 수 있다

### 다형성의 장점
1. 객체는 항상 역할에 의존해야지 구현체에 의존하면 안됨
  - 내가 편의점 사장이야, 알바라는 역할이 잇잖아
  - 알바한테 역할을 의존을 해야지 알바생중에 장동건을 의지하면 안된다.
  - 누구든 알바의 역할을 대체해야함
  - 뮤지컬을 해야하는데 조승우를 뽑음, 조승우에 의존을 하게 되면 공연을 못함.
2. 배열을 이중모음 구조로 만들 수 있음

- 오버라이딩을 해주자

### 자바빈
-  객체의 데이터를 가진 데이터

### boolean
- boolean 타입의 getter는 isCoupon() 형식 관례임

### static
- static 데이터는 생성자에서 초기화하면 안됨
- static 필드의 초기화는 static initializer를 사용
- 자동호출된다.
- 제어의 역전, 의존성 주입
```java
public static Scanner sc;

static {
    System.out.println("정적 초기화자동 호출");
    sc = new Scanner(System.in);
}
```
## MVC
- Controller : Java (중간처리)
- Repository : DB
- View : Javascript