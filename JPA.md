### JPA란?
- 자바 객체와 관계형 DB간의 매핑처리를 위한 API.  
- ORM 사용을 위한 인터페이스를 모아둔 것.  
- 실제 사용을 위해선 JPA를 구현한 구현체를 사용해야 한다.   
- 구현체는 Hibernate, OpenJPA등이 있다.
- JPA, Hibernate, Spring Data JPA 개념도
   ![image](https://github.com/user-attachments/assets/112689c7-cc0a-4671-afea-af8aa61a2d7f)
   - JPA와 Hibernate는 데이터베이스 매핑을 위한 기술이고, Spring Data JPA는 JPA 사용시 발생하는 반복적 코드를 줄여주는 기술이다.  

### JPA 사용이유
1. 자바 객체를 사용하듯 DB에 접근하여 CRUD가 가능하다.  
   - 비지니스 로직 집중
   - 재사용성 증가로 유지보수 용이
   - SQL 작성안함, 값 설정이나 변수선언등의 부수적인 코드 작성이 줄어든다.
   - 테이블이 하나의 객체(엔티티)가 되어 코드 가독성이 올라감
2. DBMS에 대한 종속성이 줄어듬
   - DBMS가 변경되더라도 소스를 변경할 필요가 없다.
### JPA 내부구조 
   ![image](https://github.com/user-attachments/assets/9096153d-c4fb-4858-abfb-27279c598755)
   - EntityManager
      - JPA는 EntityManager 클래스를 통해 엔티티들을 관리
      - 내부적으로 영속성 컨텍스트를 가지고 있다.
         - EntityManager는 DB에 가기전에 이미 조회된 값인지 영속성 컨텍스트에서 확인한다.
         - 만약 영속성 컨텍스트에 값이 있으면 DB까지 가지않고 영속성 컨텍스트에 저장된 값을 바로 리턴하고 값이 없으면 DB에서 값을 조회한 뒤 영속성 컨테스트에 저장하고 결과값을 리턴한다. 이 것을 1차캐싱이라고 한다.
       ![image](https://github.com/user-attachments/assets/5f9bb66d-3662-436c-8461-20603dd61dc3)
   - 내부구조에 대해서 더 궁금하면 참고
      - https://devraphy.tistory.com/513    
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
  
