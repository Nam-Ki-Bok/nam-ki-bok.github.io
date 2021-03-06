---
title:  "[Python] 기초 튼튼 다지기 Try Except File"
excerpt: ""

categories:
  - Python

tags:
---

## Try.. Except.. Finally

우리가 만든 프로그램은 정말 수 많은 오류를 가지고 있을 것이다.

그렇기 때문에 우리는 프로그래밍을 하면서 예외처리를 해주어야한다.

바로 Try Except 문을 사용해서 !

처음에 연습하는데 try catch 문으로 코딩하고 있었다..

자바는 try catch 니까 헷갈리지 말자 !

겸사겸사 기억할겸 file open 예제를 통해 같이 공부해보자

```python
try:
  f = open("textFile.txt", "r")
  print(f.read())
except:
  print("File Open에 실패했습니다.")
else:
  print("File Open 성공!")
  f.close()
finally:
  print("수고하셨습니다 !")
  
```

차례차례 설명해보자면 맨 처음 try 문에서는 내가 원하는 실행 코드를 입력하면 된다.

여기선 textFile 이라는 txt 파일을 읽기 모드로 열었다.

만약 파일을 여는데 문제가 발생한다면 except 문에 있는 문장을 출력 후 finally 문에 있는 문장을 출력한다.

만약 파일을 여는데 성공했다면 else 문에 있는 문장을 출력 후 finally 문에 있는 문장을 출력한다.

정리하자면

try : 실행 코드 위치

except : 오류 발생 시 실행 코드 위치

else : try 문 실행 후 오류가 없는 경우 실행 코드 위치

finally : 어떤 일이 있어도 무조건 마지막에 실행 되는 코드 위치 이다.

## File

이번엔 다른 파일을 가져와 파이썬으로 수정, 생성, 삭제 하는 연습을 해보자

개인적으로 다른 외부 파일을 가지고 같이 코딩하는게 제일 재미있는 것 같다.

파일을 가져오는 방식으로는 세 가지가 있다.

w : 쓰기 모드

r : 읽기 모드

a : 추가 모드

```python
# 쓰기 모드
f = open("test.txt", "w")
f.write("쓰기 모드는 기존의 file 내용 위에 덮어 씌운다.")
f.close()

# 읽기 모드
f = open("test.txt", "r")
print(f.read())
f.close

# 추가 모드
f = open("test.txt","a")
f.write("추가 모드는 기존의 file 내용의 마지막에 이어 붙여진다.")
f.close
```

file 사용을 했으면 마지막엔 꼭 꼭 꼭 f.close() 를 통해 닫아주자 !!!