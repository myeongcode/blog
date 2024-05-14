+++
author = "우명규"
title = "[Baekjoon] 2439번 문제"
date = "2024-05-14"
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

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/8f3b9705-b0b6-4776-b837-bfd7eee915c1)

## 풀이

그냥 별찍기로 하면 쉽게 풀 수 있었는데.. 오른쪽으로 정렬해야한다고하니 어떻게 해야할지 막막했다.. 단순히 별찍기인데..

어쨋든, 별 찍을 개수를 입력받고 입력받은 값에 별찍을 i만큼을 공백으로 채워주고 그 뒤에 \*을 i만큼 출력해주도록 작성했다.

```python
inputCnt = int(input())

# 1부터 inputCnt까지의 범위를 설정
for i in range(1, inputCnt+1):
  # 입력받은 inputCnt에서 i만큼을 공백으로 채우고 뒤에 나머지를 *로 채움
  print(" "*(inputCnt - i) + "*"*i)
```

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/acde7640-e912-4566-b1cf-557738e148c2)

> 해결완료 ✅
