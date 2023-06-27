# AWS08

## 리액트 AWS 배포
- API 점검
- [ec2]$ lsof -i:80
- [ec2]$ sudo su
- [ec2]# cd /usr/local/project/todo-api202306/
- 코드를 바꿔야 되는 상황이면 git을 통해 수정하는게 올바른 방법
- 윈도우 환경에서 인텔리제이로 고친다
- allowedOrigin("*")
- [ec2]# git fetch
- [ec2]# clear
- [ec2]# git log --oneline --all --graph
- [ec2]# git pull origin master
- [ec2]# ./gradlew clean
- [ec2]# ./gradlew build
- 