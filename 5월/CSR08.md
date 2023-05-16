# CSR08

## 파일업로드
- 웹에서 첨부파일, 이미지
- 드래그앤 드롭방식
- 파일 경로를 찾는 방식 <- 인기
- 파일을 전송하기 위해선 GET 방식은 불가능
- input태그의 file 타입을 작성
- name은 DTO와 맞춰야함
- 파일업로드 같은 경우는 모든 파일(*)로 하면 안됨
- why? php 등 악성코드를 배포할 수 있기때문
- accept="image/*"  (png, jpg ...)
```html
 <form action="/upload-file" method="post" >
        <input type="file" name="thumbnail" accept="image/*" multiple>
    </form>
```
- 파일을 여러개 선택하고 싶으면 multiple 옵션을 씀
- 하지만 갯수제한을 못두기 때문에
- 첨부파일 갯수별로 (+)로 관리함 즉 아래처럼 관리
```html
<input type="file" name="thumbnail" accept="image/*" >
<input type="file" name="thumbnail" accept="image/*" >
<input type="file" name="thumbnail" accept="image/*" >
```
- input창 CSS는 별로 안이쁨
- 박스를 하나 만들어서 input창에 display none으로 선태감
- onclick 이벤트를 걸어서 click을 검
```javascript
<script>
        const $box = document.querySelector('.upload-box');
        const $input = document.getElementById('img-input');

        $box.onclick = e => {
            $input.click();
        };
    </script>
```

- 매개변수 MultipartFile를 써야함
- 파일서버, 클라우드에 파일을 저장함
- DB는 파일이 어디있는가에 경로(위치)만 저장함
### 디테일 처리
- 보유기한 설정(폴더를 날짜별로 관리)
- 파일 이름 중복 처리

### GITHUB에 올리면 안되는 파일
- application.properties
- config 파일들

### Properties
- 파일 업로드 루트 경로, DB 번호같은거는 properties 파일로 키 값으로 관리하자(맘대루)