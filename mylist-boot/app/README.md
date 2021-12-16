# 02 메서드 다루기

- 특정 기능을 수행하는 코드에 대해 메서드로 정의해두면 재사용이 쉽고 코드 유지보수가 쉽다.
- 코드를 메서드로 분리하는 경우
  - 유사한 코드가 여러 곳에서 중복 사용될 때
  - 코드의 기능을 명확하게 설명하고 싶을 때


## 백엔드 개발 실습

### 1단계 - 한 사람의 연락처 정보를 문자열로 만드는 코드를 메서드로 분리한다.

- ContactController.createCSV() 정의
  - add() 변경
  - update() 변경
  - 백업: ContactController.java.01

### 2단계 - 이메일로 연락처를 찾아 배열 인덱스를 알아내는 코드를 분리한다.

- ContactController.indexOf() 정의
  - get() 변경
  - update() 변경
  - 백업: ContactController.java.02

### 3단계 - 배열 항목 삭제 코드를 분리한다.

- ContactController.remove() 정의
  - delete() 변경
  - 백업: ContactController.java.03

### 4단계 - 배열 크기를 자동으로 늘린다.

- ContactController.add() 변경


- 화면 구현
  - /static/contact/index.html 생성
    - 0: 기본 화면
    - 1: 테이블 추가
    - 2: 연락처 배열 준비 및 각 항목 확인
    - 3: 문자열에서 이름, 이메일, 전화, 회사 정보 추출
    - 4: 테이블에 추가할 tr 태그 생성
    - 5: tr 태그를 테이블에 추가
- REST API 구현
  - com.eomcs.mylist.ContactController.list()
- 화면과 REST API 연동
  - /static/contact/index.html 변경
    - 6: AJAX를 이용하여 서버의 REST API와 연동하기





#
