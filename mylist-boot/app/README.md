# 08.2 DAO 역할 도입: 인터페이스 도입하여 DAO 사용 규칙을 통일하기

- DAO 사용 규칙을 정의하여 프로그래밍의 일관성을 확보한다.

## 백엔드 개발 실습

### 1단계 - 인터페이스로 DAO 사용 규칙을 정의한다.

- com.eomcs.mylist.dao.BoardDao 인터페이스 정의
  - DAO 객체에 대해 호출하는 메서드의 시그너처를 정의한다.
  - 일관된 호출이 가능

### 2단계 - 기존의 XxxBoardDao를 인터페이스 규칙에 따르도록 변경한다.
- com.eomcs.mylist.dao.XxxBoardDao 클래스 변경
  - BoardDao 규칙에 따라 클래스를 작성한다.

### 3단계 - XxxBoardDao를 사용할 때 인터페이스 규칙에 따라 사용한다.

- com.eomcs.mylist.controller.BoardController 클래스 변경
  - BoardDao 규칙에 따라 DAO 객체를 사용한다.


## 프론트엔드 개발 실습








#
