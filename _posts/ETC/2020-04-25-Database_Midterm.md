---
title:  "[Database] Midterm Assignment"
excerpt: ""

categories:
  - 3-1
  - Database

tags:
  - 데이터베이스
---

- # Database

  Database 중간 대체 과제 프로젝트 임시 저장 POST 입니다.

  

  ## 요구사항
  
  1. 기존에 주어진 데이터베이스에서 Book, Orders, Customer Table에 각각 10개, 10개, 5개의 새로운 튜플 추가
  
  2. 초기화 버튼 : 본인이 추가한 데이터를 포함해서 3개의 테이블에 대한 데이터를 초기화 한다. 
  
     즉, book/orders 테이블은 20개의 튜플로 초기화 하고, customer 테이블은 10개 튜플로 초기화 한다.
  
  3. 입력1 버튼 : orders 테이블에 새로운 튜플을 추가한다. 새로운 데이터는 키보드에서 입력받도록 UI를 구성한다.
  
     단, 제약조건을 벗어난 입력값에 대해서는 적절한 오류 메시지를 표시하고 입력이 안 되어야 한다. 
  
  4. 검색1 버튼 : select * from book 쿼리를 실행한 결과를 표시한다.
  
  5. 검색2 버튼 : select * from orders 쿼리를 실핸한 결과를 표시한다.
  
  6. 검색3 버튼 : select * from customer 쿼리를 실행한 결과를 표시한다.
  
  <br>

현재 구현 완료 : 초기화 , 검색1, 검색2, 검색3 완료 !

현재 구현 완료 : 입력 UI 구현 완료 !

내일 해야 할 일 : 입력 UI 통해 데이터 값 읽어와서 데이터베이스에 INSERT 하기

<br>

2020-04-26 (일)

기능 구현 전부 완료 !

주석 달고 코드 리팩토링 하면 끝 !

그리고 제약조건 위반한 입력 발생 시 오류 메시지 콘솔 창에 띄우는지 UI에 띄우는지 메일 확인 할 것

<br>

2020-04-27 (월)

메일 확인 결과 오류 메시지는 원하는 곳에 띄우면 됨

UI에는 오류가 발생했으니 콘솔창을 확인하라는 메시지 출력

데스크탑과 맥북에서 모두 동작하는 것 확인

수요일에 코드, 주석 더 다듬어서 제출하기 !

<br>

2020-04-28 (화)

초기화 요구 조건을 잘못 이해하고 있었음. 스키마만 남기고 다 지운 후 초기화 시켜줘야 했다.

스키마만 남기고 다 지우는 작업을 조교님이 하고 나는 INSERT 만 구현하면 되는 줄 알았다.

다시 정확하게 과제 요구사항대로 수정 완료.

<br>

2020-05-02 (토)

제출 하루 전 최종 정리.

요구사항 전부 동작하는지 확인 후 자잘한 코드 리팩토링.

Data 삽입 &rarr; Data 삽입 오류 이 순서대로 동작 되었을 경우 UI에 Data 삽입 성공 문구는 그대로 남아 있고 

콘솔창에 에러 출력이 되었다. 그래서 에러 메시지를 전부 UI 창에 띄우는 것으로 수정.

<br>

2020-05-07 (목)

점수 확인 결과 100점 받았다 ! 