### JPA란?
자바 객체와 관계형 DB간의 매핑처리를 위한 API.  
ORM 사용을 위한 인터페이스를 모아둔 것.  
실제 사용을 위해선 JPA를 구현한 구현체를 사용해야 한다.   
구현체는 Hibernate, OpenJPA등이 있다.   
### JPA 사용이유
1. 자바 객체를 사용하듯 DB에 접근하여 CRUD가 가능하다.  
   - 비지니스 로직 집중
   - 재사용성 증가로 유지보수 용이
   - SQL 작성안함, 값 설정이나 변수선언등의 부수적인 코드 작성이 줄어든다.
   - 테이블이 하나의 객체(엔티티)가 되어 코드 가독성이 올라감
2. DBMS에 대한 종속성이 줄어듬
   - DBMS가 변경되더라도 소스를 변경할 필요가 없다.
   
### MySQL 세팅
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
  
