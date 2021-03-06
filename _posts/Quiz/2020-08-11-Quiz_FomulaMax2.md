---
title:  "[Programmers] 수식 최대화 코드 분석"
excerpt: ""

categories:
  - Quiz

tags:
---

## 수식 최대화 코드 분석

<a href="https://nam-ki-bok.github.io/quiz/Quiz_FomulaMax/" style="color:#0FA678">나의 풀이</a>

풀긴 풀었지만 파이썬 답지 않은 느낌이 아주아주 강한 내 코드..

다른 사람 코드들 중 보자마자 정말 파이썬 답고 예쁘다는 느낌이 들었던 코드가 있다.

```python
import re
from itertools import permutations


def solution(expression):
	op = [x for x in ['*', '+', '-'] if x in expression]  # 주어진 식의 연산자 추출
	op = [list(y) for y in permutations(op)]  # 추출한 연산자의 우선순위 경우의 수
	ex = re.split(r'(\D)', expression) # re.split('([^0-9])', expression) 와 같은 결과


	a = []
	for x in op:  # 연산자의 우선순위 경우의 수
		_ex = ex[:]  # 식을 바꿔가며 계산하니까 내가 했던 deepcopy 와 같은 기능으로 추정
		for y in x:  # 우선순위 연산자 한 개 추출
			while y in _ex:  # 추출한 연산자 모두 계산
				tmp = _ex.index(y)  # 연산자의 index 계산 후
				_ex[tmp-1] = str(eval(_ex[tmp-1]+_ex[tmp]+_ex[tmp+1]))  # 양 옆의 숫자와 계산한 값을 연산자 왼쪽 index 에 삽입한다
				_ex = _ex[:tmp]+_ex[tmp+2:]  # 계산에 사용한 연산자와 오른쪽 숫자를 자른뒤 붙인다
		a.append(abs(int(_ex[0])))  # 최종 계산 결과를 절댓값을 붙인 정수로 저장한다

	return max(a)
```

일단 정리하자면 내가 풀었던 알고리즘과 100% 일치한다..

그런데 이렇게 깔끔하게 코드를 짤 수 있다는게 정말 감탄 밖에 나오지 않는다 !!!

---

**1. 연산자 우선순위 경우의 수 만들기**

나 같은 경우는 어차피 연산자가 두 개가 있든 세 개가 있든 세 개로 했을때의 우선순위 경우의 수를 만들어 계산하면 됐기 때문에

미리 만들어 두었다. 하지만 이 코드는 정말 주어진 연산자만 추출해 우선순위 경우의 수를 만든다.

그렇담 조금이라도 계산할때 시간이 단축되고 문제의도에도 더 맞는 것 같다..

**2. 주어진 문자열을 리스트로 나누기**

나 같은 경우는 정말 일반적으로 문자열을 계속 반복하면서 연산자가 나오기 전 까지 숫자를 만들고 넣고 연산자 넣고.. 반복했다.

하지만 이 코드는 정규식을 사용한다. \D 를 사용하거나 [^0-9]를 사용하면 숫자가 아닌 문자를 기준으로 split 을 해서

['50', '6', '3', '2'] 숫자만 추출한다.

그런데 아직까지 이해가 가지 않은 궁금증이 있다. 코드에서처럼 소괄호로 (\D), ([^0-9])를 묶으면

['50', '\*', '6', '-', '3', '*', '2'] 연산자 까지 포함해서 split 을 한다. 검색을 해보니 그룹화를 한다는 것 이라는데.. 아직 이해가 안간다.

**3. 우선순위 경우의 수를 통해 계산하기**

1, 2 번 과정보다 이 알고리즘을 이렇게 코딩했다는게 정말 간결해서 신기했다.

분명히 나랑 같은 알고리즘인데.. 그래서 한 줄 한 줄 분석을 해봤다.

리스트도 [:] 를 통해 자를 수 있다는 것을 정말 까먹고 있었다..

나는 deepcopy 를 사용해 복사를 했지만 이 코드는 ex[:] 를 사용해 가져온다.

그리고 while in 처리가 정말 좋았다. 그렇게 되면 while 문 안으로 들어와서 연산자를 다시 체크 할 필요도 없다.

또 _ex 를 자르고 붙여도 in 으로 검사를 하기 때문에 반복문에 영향을 주지 않는다.

또또 몰랐던 사실이 있는데 eval 함수를 모르고 있었다..

eval('25+10') 을 하면 35가 반환된다. 문자열로 이루어진 수식을 넣으면 계산을 해준다..

그리고 _ex[:tmp] + _ex[tmp+2:] 를 통해 계산한 수식을 자르고 붙인다..

---

내가 생각한 알고리즘과 똑같은데 이렇게 코딩 할 수 있다는 사실에 정말 신기했다.

이 문제를 통해 배운게 아주 많은 것 같다.

더 파이썬 답고 쉽게 코딩 할 수 있게 노력해야겠다 !!!!!

