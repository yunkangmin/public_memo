### 프로젝트 설정 참고
- https://github.com/yunkangmin/public_memo/blob/main/%EC%8A%A4%ED%94%84%EB%A7%81%EB%B6%80%ED%8A%B8%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0.md  
mysql driver 라이브러리도 추가해준다. 


### 데이터베이스 설치와 환경설정 참고 
- https://github.com/yunkangmin/public_memo/blob/main/docker%EB%A1%9C%20mysql%20%EB%9D%84%EC%9A%B0%EA%B8%B0.md  
- https://github.com/yunkangmin/public_memo/blob/main/JPA.md  

### 데이터 베이스 설정
application.yml(yml형식으로 사용하려면 porperties를 yml로 변경하기만 하면 됨)
```yml
spring:
  application:
    name: demo
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    username: root
    password: 1212
    url: jdbc:mysql://localhost:3306/jpa
```
url 부분에 jpa가 접속하고자 하는 데이터베이스 이름이다. 

### 소스 참고 
https://github.com/yunkangmin/demo/tree/master/src/main/java/com/example/boardmysql

### 소스 실행은 main 함수를 실행하면 된다. 
![image](https://github.com/user-attachments/assets/a011cd95-c598-4a16-be96-560e579e3234)


















