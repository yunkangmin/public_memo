```
docker pull mariadb
docker images
docker run -p 3306:3306 --name test -e MARIADB_ROOT_PASSWORD=1234 -d mariadb
docker exec -it test bash

mariadb -u root -p
create database test;
create user 'tester'@'%' identified by 'tester1234';
create user 'tester'@'localhost' identified by 'tester1234';
grant all privileges on *.* to 'tester'@'%';
flush privileges;
```
