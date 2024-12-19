### 도커란? 
  - 컨테이너 기반의 가상화 플랫폼
  
### 컨테이너
  - 프로세스를 격리해 독립된 환경을 만드는 기술
### 가상화 플랫폼 
  - 게스트 프로그램을 만들어 독립된 환경을 만드는 기술 
### 독립? 
  - 독립된 하드웨어에서 소프트웨어를 실행하는 것처럼 보이게 하는 것
### 도커로 MySQL을 띄우는 이유
  1. 포트 중복 방지 
  2. 독립적으로 운영
     - 잘못 설치해도 컨테이너만 지우고 다시 설치하면 됨 
### 윈도우에 도커 설치 
  - https://www.docker.com/products/docker-desktop/
### 버전 확인
  - docker -v
### MySQL 이미지 다운(docker desktop을 켜놓고 실행해야함)
  - docker pull mysql
### 이미지 확인 
  - docker images
### 컨테이너 생성 및 실행
  - docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=1212 -d -p 3306:3306 mysql:latest
### 컨테이너 접속
  - docker exec -it mysql-container bash
### mysql 접속  
  - mysql -u root -p
