+++
author = "우명규"
title = "[Programmers] 피자 나눠먹기 - 1"
date = "2023-04-24"
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

![image](https://user-images.githubusercontent.com/67165016/233982701-bc6bf048-b0e9-456d-9368-79b9ecb62f26.png)

## 풀이

```javascript
/*
  [programmers / 피자 나눠먹기 - 1]

  입출력 예
  n	result
  7	1
  1	1
  15	3
*/

function solution(n) {
  let defaultSlice = 7;
  let person = n;

  const result = Math.ceil(person / defaultSlice);

  return result;
}
```

기본적으로 피자 1개에 7조각으로 나뉘어주는데 피자조각보다 먹어야하는 사람이 더 많을경우 소수점으로 나오므로 올림을 하여 피자의 개수를 늘리도록 함.

![image](https://user-images.githubusercontent.com/67165016/233984255-a0f86287-81de-473a-8c1a-42151b38cb83.png)

> 완료 ✅
