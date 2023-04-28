+++
author = "우명규"
title = "[Programmers] 아이스 아메리카노"
date = "2023-04-28"
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

![image](https://user-images.githubusercontent.com/67165016/235189315-3bb22410-224d-499d-b7d2-934d9504996b.png)

## 풀이

```javascript
/*
  [programmers / 아이스 아메리카노]

  money	  result
  5,500	  [1, 0]
  15,000  [2, 4000]
*/

function solution(money) {
  let americano = 5500;
  let americano_cnt, remain_money;

  americano_cnt = parseInt(money / americano);
  remain_money = parseInt(money % americano);

  return [americano_cnt, remain_money];
}
```

쉽게 몫과 나머지를 구하면 아메리카노의 잔 수와 잔돈을 알 수 있다. 정수로 return해줘야하므로 `parseInt()` 사용

![image](https://user-images.githubusercontent.com/67165016/235190866-183ccdb3-9db2-43c7-b6bb-bd36112b8556.png)

> 완료 ✅
