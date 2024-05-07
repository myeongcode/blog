+++
author = "우명규"
title = "[Baekjoon] 10818번 문제"
date = "2024-05-07"
description = "백준 알고리즘"
tags = [
    "python",
]
categories = [
    "Algorithm",
]
image = 'baekjoon.png'
+++

<!--more-->

## 문제

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/2979fa7e-8b48-46be-8828-64371a6fc762)

## 풀이

첫 번째 입력은 정수를 받을 개수를 입력값으로 받고, 두 번째 입력에는 최대값과 최소값을 구할 값들을 공백을 기준으로 입력받아 리스트에 정수형으로 넣어준다.
그리고나서, 해당 리스트에 있는 최대값과 최소값을 구하기 위해 python에서 사용되는 `min()`과`max()`를 사용하여 간단하게 최소값, 최대값을 얻을 수 있도록 해주었다.

```python
# 정수 개수 입력받기
inputCnt = int(input())
# 값 입력받기
nums = input().split()
# 받은 입력 값을 정수로 변환
nums = [int(num) for num in nums]

# 입력받은 개수와 입력받은 값의 개수가 일치한다면
if(len(nums) == inputCnt):
  # 해당 리스트에서 최대 값을 할당
  maxNum = max(nums)
  # 해당 리스트에서 최소 값을 할당
  minNum = min(nums)

print(minNum, maxNum)
```

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/72952a16-6ece-4ac8-854b-d214e5bfe691)

> 해결완료 ✅
