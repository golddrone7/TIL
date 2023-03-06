팀플?

<img src ="https://blog.kakaocdn.net/dn/bbb6Cg/btqSgNuWnsq/au9GqZaCudoiHQolkSPOL0/img.png"/>
git fetch origin   로컬에서 작업할 때 fetch를 하는 습관
git pull origin master << 에디터 나오면 충돌
git log release --oneline  릴리즈 브랜치 버전 확인

git switch -c release master 
로컬에 변경사항 (dream.txt)이 있다면 (마스터 브랜치 -> 다른 브랜치 경우)
1. 수정 사항이 의미가 있다면 커밋
2. 수정 사항이 의미가 없다면 리셋

커밋들을 의미, 버전을 매기고자 할 때 <태그>로 별칭을 지정

태그는 Lightweight tag 설명이 필요 없을 때, 이름만 구현
 Annotated tag 설명이 필요하고 태그 작성자 등 다양한 정보가 필요할 때 << 협업 사용
git tag [태그 이름] 현재 head가 가르키는 부분에 태그 추가함.

git tag v1.1.0  (Lightweight tag)
git tag -a apple -m "심심해서 붙인 태그"        (annotated tag, m은 설명)
하나의 커밋에 n개의 태그 지정 가능.
git tag << 만들어 놓은 태그를 목록으로 보여줌
git tag -n << 태그 목록 + 설명까지 추가됨
Lightweight는 커밋 내용, annotated tag는 태그 설명이 나옴

git show apple << 태그는 누가 붙이고, 커밋은 누가 했고 수정 사항이 나옴

[이전 커밋을 태그 붙이는 방법]
1. head를 이전 커밋으로 이동 후 태그 붙임
2. 커밋 아이디를 가지고 태그를 붙임
git tag -a v1.0.0 -m "첫번째 릴리즈 버전" 00c30c6   -m 옵션을 빼면 Lightweight tag임 

릴리즈에 버그가 생겼을 경우 hotpix를 함
git switch master
git switch -c hotfix/payment v1.1.0    (v1.1.0버전에 브랜치가 생김)
오류를 수정하고
git commit -am "v1.1.0 hotfix - 취미 영어로 수정"
git switch release
git merge hotfix/payment
v1(대규모).1(단순한).0(버그 픽스)
git tag -a v1.1.1 -m "hotfix"       오류 수정 tag 커밋을 덧붙임
git branch -d hotfix/payment
git push origin release 변경사항을 깃허브에 올리기
git push origin --tags 로컬에서 만든 태그도 원격에 따로 올리기

태그는 다른 브랜치에서도 필요하면 활용하면 됨
로컬에 태그 붙여도 원격에만 안올리면 됨 (release만 올리기)


<h3>3장 - 팀개발</h3>

1. fork부터 상대방의 저장소를 내 저장소로 fork한다. -forked 명명
2. git clone https://github.com/golddrone7/git-study-1-forked.git 내 저장소의 forked를 클론하기
git log --oneline --all --graph 다른 사람의 작업을 logging
3. git switch -c feat/music master  다른 사람의 작업물을 새 브랜치를 만들어서 수정함
4. git commit -am "music.txt 수정함 "  상대방은 커밋한지 모름
5. git remote -v  // 현재 복제 저장소를 알 수 있음
6. git push origin feat/music
7. feat/music had recent pushes less than a miune ago 깃 허브 compare&pull request
8. 요청할 때 메시지를 보내줌 개발자 -> 팀장
9. 팀장이 검토 후 코드 리뷰, 답변, 거절, 커밋을 할 수 있음
10. 최종 승인하면 Contributors에 있음
11. 내 포크 저장소를 원본 저장소에 sync fork -> update branch (새로운 fork를 할 필요없음)
12. 로컬 갱신은 fetch 를 이용 git fetch origin 
13. git switch master, git pull origin master
포크 원격 저장소를 동기화, 로컬 원격 저장소를 동기화 작업을 한번에
(1)원본 저장소를 추가한다  git remote add upstream https://github.com/Createcoding/git-study.git
(2)git fetch upstream (원본에 변경사항을 확인하고)
(3)git pull upstream master  (원본에는 pull 만 가능)
(4)forked 저장소에 push를 한 다음에 pull request를 보내기

신뢰하는 사람은 push 권한을 줄 수 있음(팀플을 할 때 oraganization)
forked는 pull request를 해야함.


new Organization -> 단체이름, 이메일, My personal account -> 승인
Triage 권한
Write 권한 Push까지 가능

<h4>미니 팀플 과제 github 협업해보기 </h4>
주제 : 위키문서 만들기
쥬라기 공룡 정보 만들기

공룡의 분류
 -육지공룡
  ㄷㄷㄷ

merge 는 팀장만 하고
pull request하기

팀원은 무조건 master에 커밋, 푸시 금지
master에는 무조건 병합커밋만 존재해야함.
팀원들은 각자의 브랜치에 내용을 커밋하고 
브랜치를 푸시하고 팀장에게 PR을 보낸다

팀장은 해당 브랜치를 검토하고 병합여부를 결정
병합이 완료되면 모든 팀원은 master를 pull받고 작업을 이어간다.


원격 마스터랑 로컬 마스터는 병합을 하기 위한 용도로만 사용하기

Git-Flow

개발을 하는 시간보다 문서를 작성하는 시간이 훨씬 많음
함수명, 디자인패턴, 데이터베이스 스키마 설계, 변수명....
협업을 할 때도 브랜치 전략을 말함

ex)master는 절대 push를 하지 말고 merge만 (완성된 버전),
  hotfixes 파일, release(bug), develop(test), feature branchs(release branch 병합)...
개발자들 끼리의 약속.

master : 기준이 되는 브랜치, 제품을 배포하는 브랜치
develop : 개발 브랜치, 각자 작업한 기능을 합침
feature: 단위 기능을 개발(조회, 댓글), 기능 개발이 완료되면 develop 브랜치에 합침
release: 배포를 위해 master브랜치를 보내기 전에 테스트를 하는 브랜치
hotfix: master브랜치로 배포를 했는데 버그가 생겼을 때 긴급 수정하는 브랜치
ㄴ 상식에 벗어나는 행동을 하게 되면 버그가 발생함. 개발 의도에 벗어 날 때 사용

잘만들어진 깃 플로우
<a href="https://github.com/golddrone7/TIL/blob/main/3%EC%9B%94/README%EC%96%91%EC%8B%9D.md">ItsenPjt</a>

Readme 파일
너네 저장소에 흥미를 끌 수 있고 너의 프로젝트에 이해를 돕기 위해 ReadMe 파일을 작성해라
(어떤 도움을 줄 수 있는지, 환경 설정은 어떻게 하고 어떤 기능이 있는지 설명하는 파일)
git switch -c feat/readme master
touch README.md    (깃허브에서 README 파일을 인식함 md는 마크다운을 의미, .git이 있는 루트 경로에 작성하기)
notepad readme.md

예제
# Git을 열심히 공부하는 저장소

---

## 공부 기간
- 2023.03.02 ~ 2023.03.06

## 배운 내용들
1. 로컬 저장소에서 버전관리하기
- 주요 개념: init, add, commit, log, status
2. 원격 저장소에서 버전관리하기
- 주요 개념 : remote add, push, fetch, pull...
3. 브랜치 관리하기
- 주요 개념 : branch, merge
4. 커밋 이력 관리하기
- 주요 개념 : reset, amend, rebase, cherry-pick

git add .
git commit -m "readme 파일 추가하기"

git fetch
git pull
git push origin master

git을 모르는 이유??
git flow 협업을 시작한 역사가 길지 않음 (14~15년)

<img src="https://heropy.blog/css/images/vendor_icons/html5.png"/>

* 빠르게 개발 하는 방법
물고기를 잡는 방법을 알아야함 -> 구글링의 한계 -> 공식 레퍼런스 보기(혼자서 할때 보는 연습)

## HTML이란? 구조를 만드는 언어
ex)HTML(구조) : 건설사, 토지가 있으면 철근을 박아야함. 구역(Patition)을 나눔(1,2,3층, 거실, 화장실...)
ex)CSS(인테리어) : 장판은 대리석, 벽지, 비데.. 
ex)JavaScript(기능) : 수돗물, 문 열리는 기능, 서랍 열리는 기능..
```
HTML 자체로 CSS 작업을 하면 안됨
<h1>태그는 제목을 쓰는 용도(제일 중요함), 글씨 크기를 조절하는 기능아님, 글씨 크기는 CSS이 담당
<h2> h1~h5는 중요도를 의미
많이 하는 오해 ! 글씨 크기를 조절하는 기능아님, 글씨 크기는 CSS이 담당
CSS 작업을 하기 전엔 reset을 함

태그 :  <> </> 태그 한 쌍을 요소라 불림   
요소(=태그) :  <p></p> p요소, 편의상 p태그라 함
마크업 : 요소들을 이용하여 웹 문서를 작성
속성 : 태그의 요소에 지정하는 것들

<TAG 속성="값"> </TAG>
<TAG 속성="값" 속성="값"><TAG>
<a href="www.naver.com" class="naver-link"></a> class는 별명을 지님
<부모태그> 1개의 부모는 n개의 자식을 가짐
 <자식태그></자식태그>
 <자식태그></자식태그>
 <자식태그></자식태그>
</부모태그>
부모, 형제, 자식 관계, 조상 관계(할아버지, 증조, 고조, 부모), 자손(후손) 관계

<!doctype html> 선언문   doc 문서 type 타입은 html 이다.
<html></html> 형제는 head와 body만 들어감
<head></head> 문서의 속성, 설정 정보, meta 데이터를 설명하는 데이터
<body></body> 비쥬얼적인 UI
```
meta를 잘 적어야 검색 엔진에 잘들어감 최적화(SEO)
title 문서의 제목
link CSS 파일 연결
script 자바스크립트
style CSS

HTML CSS JAVASCIPT React => Visual studio code에서 진행

D드라이브 html-css-study 생성
File - open folder - D:\html-css-study - 폴더선택 - 신뢰하기 

market place -> 
korean (visual code 한글설정)
material theme icons(폴더 아이콘), material theme (테마 바꾸기)
파일-기본설정-설정, 워크밴치->모양->color theme
파일-설정-바로가기 키-키바인딩 검색("글꼴")-편집기 글꼴 축소  (컨트롤 -), 확대(컨트롤 +)지정

Readme 파일 작성, 오른쪽 위 책모양돋보기 클릭하면 마크다운 언어 적용 된 모습을 볼 수 있음
파일 -> 자동 저장 활성화
! tab : html 자동 완성
h${안녕$}*6 (emmet 문법)
auto rename : 앞에 태그를 적으면 뒤에 태그 자동 완성 기능 (마켓플레이스)
윈도우 방향키(왼쪽, 오른쪽) 화면 왼쪽, 오른쪽 분할
live server : 새로고침을 안해도 자동으로 바뀜(마켓플레이스) 
beautify : 자동정렬 편하게 ( 줄 그임 표시는 더이상 업뎃안하겠다는 의미)
		Ctrl + alt + L
power mode : ???

유료툴은 기본으로 다 설치되어있지만, 무료툴은 다 설치를 해줘야 함


블록 요소 : 영역을 만드는 것
인라인 요소 : 텍스트를 만드는 것

개발할 땐 폴더, 파일명은 영어로 하는 것이 좋음

블록요소는 마크업시 자동 줄바꿈, 블록 요소는 또 다른 블록, 인라인 요소를 포함,
 최대 가로 너비를 점유, 가로, 세로 크기를 지정 가능
 div, h1~6, p 왠만하면 블록요소고 몇개의 인라인 요소만 외우면 됨.

인라인요소는 마크 다운 시 줄바꿈이 일어나지 않음, 인라인 요소 안에는 인라인만 가능하다.

h1~h6 제목을 수정하기 위한 태그   제일 중요한 태그는 h1
* h1 없는 h2는 없다. <h1> <h2> <h3> ... 순서대로! 작성하기
건너뛰지 말기!!!, 글씨 크기를 위해 제목 태그를 사용하지 마세요
h1 태그는 딱 1개만 2개부턴 SEO 최적화가 안됨. 
h2태그 이후 부턴 n개 작성 가능 h4~h5는 실제론 잘 안나옴 

웹 접근성 : 모든 사람이 평등하게 사용하기
 ex) (시각 장애인)스크린 리더기 이미지를 보조하는 텍스트 alt, 확대 축소 버튼 넣어주기

header 태그 : 로고, 검색창, nav를 통틀어서 말함  
footer 태그 : 사이트의 제일 하단 부,   
section 태그 : 구역, 영역, h1~h6 필요 ex)광고, 로그인, 뉴스스탠드 배너 ...
aside 태그 : 사이드 바
nav 태그 : 페이지 링크
div 태그 : 깡통 태그, 제목이 없을 때 또는 최후에 설정하는 태그  

html5부터는 header 태그를 권장함, 네이버는 id로 header, footer 지정, 깃 허브는 header, footer 태그로 만듬


