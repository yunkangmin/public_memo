- MySQL 세팅
  ```sql
  -- 데이터베이스 생성
  create database jpa CHARACTER SET utf8mb4;

  -- 유저생성
  CREATE USER 'jpa1'@'localhost' IDENTIFIED BY 'jpa';
  CREATE USER 'jpa1'@'%' IDENTIFIED BY 'jpa';

  -- jpa 접근 권한부여
  GRANT ALL PRIVILEGES ON jpa.* TO 'jpa1'@'localhost';
  GRANT ALL PRIVILEGES ON jpa.* TO 'jpa1'@'%';

  -- 테이블 생성
  create table jpa.user (
    email varchar(50) not null primary key,
    name varchar(50),
    create_date datetime
  ) engine innodb character set utf8mb4;
  ```
  
