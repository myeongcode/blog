+++
author = "우명규"
title = "[Programmers] 배열 뒤집기"
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

![image](https://user-images.githubusercontent.com/67165016/235337734-1176178b-2af1-4221-8e32-a57269c3bd3d.png)

## 풀이

```javascript
/*
  [programmers / 배열 뒤집기]

  num_list	result
  [1, 2, 3, 4, 5]	[5, 4, 3, 2, 1]
  [1, 1, 1, 1, 1, 2]	[2, 1, 1, 1, 1, 1]
  [1, 0, 1, 1, 1, 3, 5]	[5, 3, 1, 1, 1, 0, 1]
*/

function solution(num_list) {
  var answer = num_list.reverse();
  return answer;
}
```

js에서 제공하는 메서드인 `.reverse()`만 사용하면 쉽다.

![image](https://user-images.githubusercontent.com/67165016/235337777-f93eb03d-ae83-448d-95ee-9cc31f9459de.png)

> 완료 ✅
