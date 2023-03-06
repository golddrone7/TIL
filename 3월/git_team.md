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


3장 - 팀개발

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

팀플

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

