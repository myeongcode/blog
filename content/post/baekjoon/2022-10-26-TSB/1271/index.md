+++
author = "우명규"
title = "[Baekjoon] 1271번 문제"
date = "2022-10-26"
description = "백준 알고리즘"
tags = [
    "python",
]
categories = [
    "Algorithm",
]
image = "baekjoon.png"
+++

<!--more-->

## 문제

![image](https://user-images.githubusercontent.com/67165016/232457122-e204f0f5-3942-4b56-9599-c829d9bd4519.png)

## 풀이

이 문제는 C언어로 풀어봤지만, C언어에서 정수형의 표현 범위는 long을 이용해도 2,147,483,647정도로 10의 1000승에 비하면 터무니없이 작은 수이기 때문에 **계산할 수 있는 범위를 벗어나서 오버플로우가 발생**했고, 출력값이 잘못 나오게 되는겁니다.

따라서, 이 문제는 C가 아닌 파이썬을 이용하면 훨씬 더 쉽게 풀 수 있다는 것을 알았습니다.

왜냐하면 **파이썬은 큰 수를 자동으로 처리해주기 때문**이죠.

```python
m, n = map(int, input().split())

print(m // n)
print(m % n)
```

![image](https://user-images.githubusercontent.com/67165016/232457663-3db1db14-493a-4a13-a2b5-3d4cb75eda31.png)
