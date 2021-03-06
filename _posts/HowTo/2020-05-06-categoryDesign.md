---
title:  "[How To] Jekyll Category 디자인"
excerpt: ""

categories:
  - How To

tags:
  - Jekyll
---

- ## Category 디자인

  Minimal Mistakes 에서 기본 제공하는 스킨을 설정해 사용 중 이었다.

  하지만 나에게 맘에 안드는 부분이 굉장히 많았다. 그래서 수정을 해볼까 마음 먹었는데 생각보다 꽤 복잡했다.

  css 파일이 분야 별로 나뉘어져 있는데 어느 파일이 어디를 적용시키는지 찾느라 시간이 좀 걸렸다.

  그래서 Minimal Mistakes 가 제공하는 가이드를 보며 겨우겨우 찾았다.

  <a href="https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/" target="_blank" style="color:green;">이 곳</a> 에서 CUSTOMIZATION 부분을 보면 왠만해선 정보를 얻을 수 있다.

  우선 제일 신경쓰이고 마음에 안들었던 부분은 블로그 상단 Cartegory 디자인이 마음에 안들었다.
  
  마우스를 올려 놓으면 밑줄이 생기는데 그 밑줄이 굉장히 굵고 텍스트에 거의 딱 붙어서 나왔다.
  
  /_sass/minimal-mistakes/_navigation.scss 파일을 수정 하면 원하는 디자인으로 만들 수 있다.
  
  <br>
  
  수정 commit 링크이다.
  
  <a href="https://github.com/Nam-Ki-Bok/nam-ki-bok.github.io/commit/d4e591f403ffce7199cc1ed202b3c9ef31dca683#diff-b8480c9e5e376f2d5eaaa9da9c649a3f" target="_blank" style="color:green">밑줄 굵기 조절</a>
  
  <a href="https://github.com/Nam-Ki-Bok/nam-ki-bok.github.io/commit/6773362cc41a0302901ff48d3d41ef199801a118#diff-b8480c9e5e376f2d5eaaa9da9c649a3f" target="_blank" style="color:green">밑줄 padding 조절</a> 
  
  앞으로 계속 수정 하면서 나에게 맞는 디자인으로 바꿔야겠다..

