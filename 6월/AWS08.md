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
- [ec2]# java -jar build/libs/todo-0.0.1-snapshot.jar
- [ec2] nohup java -jar build/libs/todo-0.0.1-snapshot.jar &
- [ec2]# tail -200 -noout
- npm start
- 리액트 앱은 S3에 배포하기
- 리액트를 EC2에 해도되긴하지만, 정적 웹페이지이기 때문에 굳이 올릴필요없음
- aws root로 모든 것을 하는 건 좋지 않은 방법
- IAM 
- [ec2]# nohup java -jar build/libs/todo-0.0.1-SNAPSHOT ~~~
- npm build
- 