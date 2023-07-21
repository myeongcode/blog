+++
author = "우명규"
title = "[Programmers] 양꼬치"
date = "2023-07-21"
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

![image](https://github.com/myeongcode/blog/assets/67165016/5ea17c15-287a-489d-8ccf-3d69e64c1408)

## 풀이

```javascript
/*
  [programmers / 양꼬치]

  n	k	result
  10	3	124,000
  64	6	768,000
*/

function solution(n, k) {
  let lambSkewers = 12000;
  let drink = 2000;

  let serviceDrink = parseInt(n / 10);
  lambSkewers *= n;
  k -= serviceDrink;
  drink *= k;

  const answer = lambSkewers + drink;

  return answer;
}
```

단순히 10인분 당 음료수 1개가 서비스니까 인분 당 서비스 개수를 구하고, k(먹은 음료수 개수)에서 serviceDrink(받을 수 있는 음료수 서비스 개수)를 뺀 값을 drink(실제 계산해야하는 값)에 넣어주면 끝

![image](https://github.com/myeongcode/blog/assets/67165016/b761cab2-d98f-4c95-99ba-295560056c3f)

> 완료 ✅
