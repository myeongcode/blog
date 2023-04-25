+++
author = "우명규"
title = "[Programmers] 피자 나눠먹기 - 3"
date = "2023-04-25"
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

![image](https://user-images.githubusercontent.com/67165016/234262096-a732b9cb-2d57-45ed-81e3-0fd931198050.png)

## 풀이

```javascript
/*
  [programmers / 피자 나눠먹기 - 3]

  입출력 예
  slice	n	result
  7	10	2
  4	12	3
*/

function solution(slice, n) {
  let defaultSlice = slice;
  let person = n;

  const pizza = Math.ceil(person / defaultSlice);

  return pizza;
}
```

[피자 나눠먹기 - 1](https://myeongcode.github.io/p/programmers-%ED%94%BC%EC%9E%90-%EB%82%98%EB%88%A0%EB%A8%B9%EA%B8%B0-1/) 처럼 기본적으로 피자 1개에 slice조각으로 나뉘어주는데 피자조각보다 먹어야하는 사람이 더 많을경우 소수점으로 나오므로 올림을 하여 피자의 개수를 늘리도록 함.

![image](https://user-images.githubusercontent.com/67165016/234264408-f65042ea-7596-42c8-948d-1322da14d737.png)

> 완료 ✅
