# CSS

- 포지션, 레이아웃 전체적으로 보고
- 전환, 변환, 애니메이션
- FlexBox를 배우기전에
- kokokaki.github.io 사이트를 clone코딩
- 2~3명
- 한사람당 1페이지, 페이지만(기능 X)
- 6개월내에 공부하기 힘듬
- 동영상을 올리면 복습 동영상 의지하게 됨 나태해짐
- 스스로를 쪼여야함
- 첫 팀플은 테이블, 이후는 제비뽑기

## 1. 박스뛰우기

### Position
- 위치지정
- `relative` 속성 상대적
- `absolute`속성 절대적
- top, bottom, left, right
- position 단독으로 쓰기보단 방향도 같이 쓰임
- 양수는 기준 방향, 음수는 반대방향
- `top:30px` 위를 기준으로 30px 내려감
- `right:40px` 오른쪽을 기준으로 40px 왼쪽으로 감
- `relative` 는 자기 기준, 주변 방해를 받지 않음
- 원래 위치에서 상대적으로 이동함 (자기 자리를 지킴)
- `absolute` 는 절대적으로 자기 마음대로 한다는 소리
- float 처럼 튀겨나옴, z축 앞으로, 자리를 뺐음
- 기준은 브라우저 화면 전체 기준임
- `relative`보다 `absolute`가 활용이 높음
- `absolute`의 이동 기준이 중요한 개념
- 부모의 absolute 기반으로 자식도 같이 움직임
- 기준은 `position:absolute;`를 붙이는 순간
- 자기 부모에게 물어봄, position이 있는지 물어보고 없으면 넘어감, 할아버지 물어봄 없으면 body 물어봄 다 없으면 브라우저 전체를 해집고 다님
- 기준을 계속 물어본 다음 할아버지가 `position:relative`가 있으면 그것이 기준이 됨
- 제일 가까운 부모에게 position이 있을 경우 그것이 기준이 됨(움직이는 제약)
- `position: static;` 기본값, none같은 의미
- `position: static;` 을 제외한 속성은 모든 것이 그 기준이 됨
- 부모가 안움직여도 자식의 위치를 제한을 걸기 위해서는 `position: relative;`를 부모에게 검
- 오해하고 싶은 변칙은 부모 안에서 움직이는 의미가 아니라 부모가 기준이 된다는 것!! 
- 기준이 다 없으면 화면 전체가 기준이 됨!
- `position : absolute`속성을 주면 인라인에서 블록으로 바뀜 대표적인 a 인라인 태그를 예시
- 인라인 속성의 태그는 position: absolute나 float 속성이 부여되면 자동으로 블록 성질로 바뀜
- 유용한 공식 
- 박스 좌우 상하 정중앙 배치 공식
- ```
    .center{
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
        }

    ```
- fixed 속성은 따라 붙을 때 사용
- position absolute는 가로길이 100% 기본값이 깨짐
- 따라서 적용하면 `width:100%`를 적용하자
- 기준이 언제나 브라우저 화면 전체

### 요소 쌓임 순서(Stack order)
- 중요한 개념
- z축 박스 순서를 말함
- header 부분은 언제나 맨 앞에 적용
- 메뉴바같은 것들
- 나중에 작성한 요소일 수록 쌓임
- position 속성이 있을 경우 가장 위에 쌓임
- 다 걸려있을 경우 나중에 작성한 요소가 쌓임
- `z-index` 의 기본값은 0
- 높을수록 위에 쌓임

### 협업, 실습 팁
- CSS 주석을 달아주자
- `/* begin container style */`
- `/* end header style */`
- `/* body layout*/`
- `/* >. side-menu */`
- `/* >. main-contnet */`
- `/* >. .banner */`
- commit 메시지를 명시적으로 써주기
- 들여쓰기 
- 게시물이 들어갈 공간은 가변적(1~10)개
- 사이드 메뉴는 고정적(5)개
- 고정적인 공간에 base 색상
- 가변적인 공간을 custom 색상
- 즉 전체적인 색상을 먼저 잡음
- `background-color`의 기본 값은 transparent 임 (투명하다는 의미)
- 즉 흰색은 흰색이라 표현해야 함

## 2. 전환, 변환
### transition
- 알면 좋은 내용
- 원본에다가 transition 속성을 검
- property
- duration
- delay를 주는 이유는 서버에서 지연된 통신이 일어날 때 쓰임
- 균일한 속도가 아님
- `transition-timing-function`은 속도를 지정
- `linear`은 같은 속도로 애니메이션 진행
- `ease` 는 처음에 빨랐다가 느려짐
- `steps(3)`은 3번에 걸쳐서 진행

### transform
- 미리 만들어놓은 애니메이션
- 