+++
author = "우명규"
title = "[Programmers] 배열의 평균값"
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

![image](https://user-images.githubusercontent.com/67165016/234265145-d3bf3287-4c62-4124-9905-06c8795d6556.png)

## 풀이

```javascript
/*
  [programmers / 배열의 평균값]

  입출력 예
  numbers	                               result
  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]	        5.5
  [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99]	94.0
*/

function solution(numbers) {
  let sum = 0;
  let answer;

  for (let i = 0; i < numbers.length; i++) {
    sum += numbers[i];
  }

  answer = (sum / numbers.length).toFixed(1);

  return answer;
}
```

배열의 개수만큼 다 더한 값을 배열의 개수로 나뉘면 쉽게 평균값을 구할 수 있다.

근데 문제에서 .0또는 .5인 경우만 정답으로 처리된다는 것 같길래 `.toFixed(1)`로 소수점 아래 1자리까지 표기해주었음.

![image](https://user-images.githubusercontent.com/67165016/234266976-27c37afe-21a4-4f6a-a1c8-9b5fec9a3a73.png)

> 완료 ✅
