# 01.1 변수 및 배열 다루기: 배열 및 입력 값 다루기

## 실습

### 1단계 - 연락처 목록 구현

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

### 2단계 - 연락처 입력 구현

- REST API 구현
  - com.eomcs.mylist.ContactController.add()
- 화면 구현
  - /static/contact/form.html 생성
    - 0: 기본 화면
    - 1: 입력 폼 추가
    - 2: 버튼 클릭 리스너 등록
    - 3: 버튼을 클릭할 때 입력 폼의 값을 알아내기
    - 4: 입력된 값을 서버에 보내기
    - 5: 취소 버튼 추가
    - 6: 리팩토링 - replace temp with query
      - 함수의 리턴 값을 받는 변수를 한 번만 사용할 경우 변수 대신 함수 호출을 삽입하라!
      - 즉 임시 변수를 사용할 자리에 함수 호출을 그대로 집어 넣어라!
    - 7: 필수입력 항목 검사하기
    - 8: 최적화 - 태그 찾기를 리스너 밖에 둔다.
    
### 3단계 - 연락처 상세보기 구현

- 화면 구현
  - /static/contact/view.html 생성
- REST API 구현
  - com.eomcs.mylist.ContactController.get()
- 화면과 REST API 연동
  - /static/contact/view.html에 AJAX 적용
