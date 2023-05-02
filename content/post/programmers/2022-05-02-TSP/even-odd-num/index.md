+++
author = "우명규"
title = "[Programmers] 짝수 홀수 개수"
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

![image](https://user-images.githubusercontent.com/67165016/235748065-38a32d85-87e4-4d20-8c12-a50358b1e143.png)

## 풀이

```javascript
/*
  [programmers / 짝수 홀수 개수]

  num_list	result
  [1, 2, 3, 4, 5]	[2, 3]
  [1, 3, 5, 7]	[0, 4]
*/

function discrimination(num_list) {
  let odd = 0,
    even = 0;

  for (let i = 0; i < num_list.length; i++) {
    if (num_list[i] % 2 == 0) {
      even++;
    } else {
      odd++;
    }
  }
  return [even, odd];
}

function solution(num_list) {
  let answer = discrimination(num_list);

  return answer;
}
```

짝수인지 홀수인지 판별하는 함수 discrimination을 만들고 return을 `[짝수, 홀수]`로 반환해줬다.

짝수인지 아닌지는 2를 나눠서 나머지가 0이면 짝수인거니까 even을 1씩 증가시키고, 2를 나눠서 0이 아니면 홀수이므로 odd를 1씩 증가시켜줬다.

![image](https://user-images.githubusercontent.com/67165016/235748299-dc0dfe55-322f-40cd-8fb9-8f0630d08c91.png)

> 완료 ✅
