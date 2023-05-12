+++
author = "우명규"
title = "[Programmers] 문자 반복 출력하기"
date = "2023-05-12"
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

![image](https://github.com/myeongcode/blog/assets/67165016/02427fd3-6986-40fb-80a4-52be67122406)

## 풀이

```javascript
/*
  [programmers / 문자열 반복 출력하기]

  my_string	n	result
  "hello"	3	"hhheeellllllooo"
*/

function solution(my_string, n) {
  var splitString = my_string.split("");
  let answer = "";
  for (let i = 0; i < my_string.length; i++) {
    for (let j = 0; j < n; j++) {
      answer += splitString[i];
    }
  }
  return answer;
}
```

그냥 문자열 개수만큼 반복하였고, 또 매개변수로 받은 n만큼 반복하여 각 문자마다 3번씩 반복하게 만들었다.

![image](https://github.com/myeongcode/blog/assets/67165016/69d7e917-1f35-4e94-8b48-059eeba7c2b4)

> 완료 ✅
