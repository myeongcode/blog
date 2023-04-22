+++
author = "우명규"
title = "[Programmers] 짝수가 싫어요 문제"
date = "2023-04-22"
description = "프로그래머스 알고리즘"
tags = [
    "javascript",
]
categories = [
    "Algorithm",
]
image = 'program-logo.jpg'
+++

<!--more-->

## 문제

![image](https://user-images.githubusercontent.com/67165016/233777974-69020128-becc-4ff7-81bc-9428fc72f37a.png)

## 풀이

```javascript
/*
  [programmers / n이하의 홀수 구하기]

  입출력 예
  n	result
  10	[1, 3, 5, 7, 9]
  15	[1, 3, 5, 7, 9, 11, 13, 15]
*/

function solution(n) {
  let oddArray = [];

  for (let i = 1; i <= n; i++) {
    if (i % 2 !== 0) {
      oddArray.push(i);
    }
  }

  return oddArray;
}
```

그냥 2로 나누어 떨어지지 않는 것을 oddArray로 push시켜주었습니다.

![image](https://user-images.githubusercontent.com/67165016/233778286-2c9c661d-dc24-4b7c-b026-dbf2435f008c.png)

> 완료 ✅
