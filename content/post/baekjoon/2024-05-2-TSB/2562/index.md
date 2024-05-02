+++
author = "우명규"
title = "[Baekjoon] 2562번 문제"
date = "2024-05-02"
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

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/9edf973b-5dbe-4017-8ac6-f98226fd6b4b)

## 풀이

최대값을 구하는 문제인 만큼 입력 값들을 서로 비교하면서 최대값에 할당을 해주면 되었다고 생각했다.

그래서 입력을 for문으로 입력을 받았고, 타입을 확인해보니 입력은 모두 String값으로 받은 것을 확인할 수 있었다. 값 비교를 위해 해당 값을 입력받았을 때 바로 정수형(int)로 변경해주었고, 전체 입력이 완료되면 for문을 통해 값을 비교하여 값의 최대값과 몇 번째에 있는지 표시해주었다.

```python
# 9개의 입력 받으면서
inputData = [int(input()) for _ in range(9)]
# 큰 수 & 인덱스 초기화
maxNum = 0
maxNumIndex = 0

# 입력받은 값을 for
for num in inputData:
  # 해당 인덱스의 값이 더 크면 최대 값 변수에 할당
  if maxNum < num:
    maxNum = num
    maxNumIndex = inputData.index(num) + 1

print(maxNum)
print(maxNumIndex)
```

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/faf3dbcc-c4cc-4dec-bedc-1325aec0045b)

> 해결완료 ✅
