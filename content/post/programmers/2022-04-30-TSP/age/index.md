+++
author = "우명규"
title = "[Programmers] 나이 출력"
date = "2023-04-30"
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

![image](https://user-images.githubusercontent.com/67165016/235337505-70c6b47d-76ac-49e8-8b32-59ae4d021fca.png)

## 풀이

```javascript
/*
  [programmers / 아이스 아메리카노]

  age	result
  40	1983
  23	2000
*/

function solution(age) {
  let default_year = 2022;
  let born;

  born = default_year - age + 1;

  return born;
}
```

2022년에 살고있었다면 `getFullYear()`를 사용했을텐데, 현재는 2023년이라서 그냥 2022년을 디폴트년도로 잡았다.

![image](https://user-images.githubusercontent.com/67165016/235337548-c91fe55e-8b28-4ba2-baec-9eff096a6853.png)

> 완료 ✅
