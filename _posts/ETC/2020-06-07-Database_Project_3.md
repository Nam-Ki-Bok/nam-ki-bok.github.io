---
title:  "[Database] 캠핑카 렌트 서비스 Project_3"
excerpt: ""

categories:
  - 3-1
  - Database

tags:
  - 데이터베이스
---

## 캠핑카 렌트 서비스 Project

테이블 설계까지 마치고 샘플 데이터를 넣어놨다. 어제까지만 해도 각각의 테이블에 샘플 데이터를 15개 씩 넣으려면 Car 테이블이

문제가 된다고 생각했다. 그런데 오늘 생각해보니 전혀 문제 될 게 없었다 !

그냥 기존에 만들어 놓았던 15개 샘플 데이터에서 차 번호만 조금씩 바꿔주면 그만이였다.

지금 이 글을 쓰는 이유는 나중에 Java 를 통해 코딩 할 때 이미지 URL 저장방법을 헷갈려 할 수도 있어 써놓는다.

예를들어 carID 가 1이면 https://nam-ki-bok.github.io/Database_Project/Car_Image/car1-1.jpg

해당 URL을 가져오면 된다. 물론 Car 테이블엔 미리 저장이 되어있지만

CarCheckList, 즉 고객이 차를 빌리고 반환 했을 경우 작성이 되는 테이블은 그때 그때 INSERT 를 해주어야 한다.

어떻게 단계가 이루어질진 아직 모르겠지만 만약 carID 가 25번인 차는 carID%15 의 값을 URL . jpg 파일 번호에 넣어주면 된다.

그리고 carID%15 값이 0 인경우에만 15를 넣어주면 된다.

근데 이것도 글 쓰다보니 생각났는데 어차피 사진은 맘대로 써도 된다고 했으니 그냥 앞, 뒤, 왼쪽, 오른쪽만 구분해주면 될 것 같다.

<a href="https://github.com/Nam-Ki-Bok/Database_Project" style="color:#0FA678">Repository</a> 에 Commit 해두었다.

