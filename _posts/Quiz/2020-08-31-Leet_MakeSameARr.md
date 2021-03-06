---
title:  "[LeetCode] 1551. Minimum Operations to Make Array Equal"
excerpt: ""

categories:
  - LeetCode

tags:
---

## 1551. Minimum Operations to Make Array Equal

<center><img src="https://nam-ki-bok.github.io/assets/images/baekjoon/makesamearr.png" style="zoom:50%;" /></center>

n 이 주어지면 초항은 1이고 등차는 2인 등차수열을 n 의 길이 만큼 만든다.

이때 index 두 개를 골라 **arr[x] -= 1**, **arr[y] += 1** 을 반복 해 배열의 모든 값을 같게 만들면 된다.

그렇다면 모든 값이 같아 질 때, 그 같은 값을 어떻게 구하면 될까 ? 바로 배열의 평균 값이 그 값이 된다.

**[1, 3, 5, 7, 9]** 가 주어진다면 더하기 1, 빼기 1 을 통해 모든 값을 평균 값인 5로 만들면 된다.

결국 배열 중에서 평균 값에서 평균 값 보다 작은 값을 뺀 수를 모두 더하면 답이 된다.

위 배열 같은 경우는 **(5 - 1) + (5 - 3) = 6** 이 된다.

---

```python
class Solution:
	def minOperations(self, n: int) -> int:
		arr = [(2 * i) + 1 for i in range(n)]
		goal_num = n
		answer = 0

		for num in arr:
			if num < goal_num:
				answer += goal_num - num
			else:
				break

		return answer


test = Solution()
n = 5
print(test.minOperations(n))
```

