+++
author = "우명규"
title = "[Baekjoon] 10699번 문제"
date = "2023-04-20"
description = "백준 알고리즘"
tags = [
    "javascript",
]
categories = [
    "Algorithm",
]
image = 'baekjoon.png'
+++

<!--more-->

## 문제

![image](https://user-images.githubusercontent.com/67165016/233321395-c170697b-656a-4e46-b14f-22961d1edcbf.png)

## 풀이

```javascript
/*
  [baekjoon / 10699]

  오늘 날짜 출력
*/

var date = new Date();
let year = date.getFullYear().toString();
let month = (date.getMonth() + 1).toString();
let day = date.getDate().toString();

solution(year, month.padStart(2, "0"), day.padStart(2, "0"));

function solution(param1, param2, param3) {
  var today = `${param1}-${param2}-${param3}`;
  console.log(today);
}
```

![image](https://user-images.githubusercontent.com/67165016/233321085-f5ff5f8e-5698-4530-81c6-4b6a5502302b.png)

![image](https://user-images.githubusercontent.com/67165016/233321226-d02aac60-1670-480a-8c13-ac08a3291d5a.png)

> 완료 ✅
