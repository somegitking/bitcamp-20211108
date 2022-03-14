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

### 2단계 - DAO 구현체에 Mybatis 프레임워크를 적용한다.

- com.eomcs.mylist.dao.mariadb.BoarDaoImpl 클래스 변경
  - SQL 코드를 뜯어내어 XML 파일로 옮긴다.
    - /src/main/resources/com/eomcs/mylist/dao/BoardDao.xml
- com.eomcs.mylist.App 클래스 변경
  - SqlSessionFactory 객체 준비

### 3단계 - DAO 구현체를 자동으로 생성한다.

- com.eomcs.mylist.dao.mariadb.BoardDaoImpl 클래스 삭제
- com.eomcs.mylist.dao.BoardDao 인터페이스 변경
  - 애노테이션을 이용하여 Mybatis 관련 설정하기
- com.eomcs.mylist.App 클래스 변경
  - SqlSessionFactory 객체를 준비하는 메서드 제거

### 4단계 - 레코드 값을 저장할 도메인 클래스의 별명을 설정한다.

- src/main/resources/application.properties 파일 변경
  - mybatis의 도메인 클래스의 별명 설정 추가
- com/eomcs/mylist/dao/BoardDao.xml 파일 변경
  - 도메인 클래스를 직접 사용하는 대신에 별명을 사용한다.
  - <resultMap></resultMap> 태그를 이용하여 컬럼과 필드를 연결한다.


### 5단계 - 자바 소스 파일과 설정 파일을 분리한다.

- BoardDao.xml 파일을 src/main/resources 폴더로 옮긴다.

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
