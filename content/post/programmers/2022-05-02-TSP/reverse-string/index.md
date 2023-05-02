+++
author = "우명규"
title = "[Programmers] 문자열 뒤집기"
date = "2023-05-02"
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

![image](https://user-images.githubusercontent.com/67165016/235729600-e3e3ec09-807e-4343-9a57-ad606154fe9c.png)

## 풀이

```javascript
/*
  [programmers / 문자열 뒤집기]

  my_string	return
  "jaron"	"noraj"
  "bread"	"daerb"
*/

function reverseString(string) {
  let splitString = string.split("");
  let reverseString = splitString.reverse();
  let joinArray = reverseString.join("");

  return joinArray;
}

function solution(my_string) {
  var answer = reverseString(my_string);
  return answer;
}
```

reverseString이라는 문자열을 뒤집어주는 함수를 하나 만들고

문자열 분해 `.split("")` ➡️ 문자열 뒤집기 `.reverse()` ➡️ 문자열 합체 `.join("")` 순으로 진행을 해주었다.

![image](https://user-images.githubusercontent.com/67165016/235729866-b1317ced-b988-4e8b-be8a-12a13be8da10.png)

> 완료 ✅
