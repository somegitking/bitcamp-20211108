# 11.1 DB 프로그래밍을 더 쉽고 간단히 하는 방법 : Mybatis 퍼시스턴스 프레임워크 도입

- JDBC 코드를 캡슐화한 Mybatis 퍼시스턴스 프레임워크 사용하기

## 백엔드 개발 실습

### 1단계 - 프로젝트에 MyBatis 라이브러리를 추가한다.

- build.gradle   
  - `search.maven.org` 사이트에서 *mybatis* 라이브러리 정보를 찾는다.
    - 직접 구성
      - `implementation 'org.mybatis:mybatis:3.5.9'`
      - `implementation 'org.mybatis:mybatis-spring:2.0.7'`
    - Spring Boot 구성
      - `implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:2.2.2'`
  - 의존 라이브러리 블록에서 `mybatis` 라이브러리를 등록한다.
- gradle을 이용하여 eclipse 설정 파일을 갱신한다.
  - `$ gradle eclipse`
- 이클립스에서 프로젝트를 갱신한다.

### 2단계 - `MyBatis` 설정 파일을 준비한다.

- src/main/resources/com/eomcs/pms/conf/jdbc.properties
  - 마이바티스 홈 : <http://www.mybatis.org>
  - `MyBatis` 설정 파일에서 참고할 DBMS 접속 정보를 등록한다.
- src/main/resources/com/eomcs/pms/conf/mybatis-config.xml
  - `MyBatis` 설정 파일이다.
  - DBMS 서버의 접속 정보를 갖고 있는 jdbc.properties 파일의 경로를 등록한다.
  - DBMS 서버 정보를 설정한다.
  - DB 커넥션 풀을 설정한다.


### 3단계: BoardDaoImpl 에 Mybatis를 적용한다.

- com/eomcs/pms/conf/mybatis-config.xml 변경
  - BoardMapper.xml 파일의 경로를 등록한다.
- com/eomcs/pms/mapper/BoardMapper.xml 추가
  - BoardDaoImpl 에 있던 SQL문을 이 파일로 옮긴다.
- com.eomcs.pms.dao.mariadb.BoardDaoImpl 클래스 변경
  - 의존 객체 SqlSession을 생성자를 통해 주입 받는다.
  - SQL을 뜯어내어 BoardMapper.xml로 옮긴다.
  - JDBC 코드를 뜯어내고 그 자리에 Mybatis 클래스로 대체한다.

## 프론트엔드 개발 실습







#
