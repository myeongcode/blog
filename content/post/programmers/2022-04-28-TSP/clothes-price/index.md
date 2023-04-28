+++
author = "우명규"
title = "[Programmers] 옷가게 할인 받기"
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

![image](https://user-images.githubusercontent.com/67165016/235184347-eeaf3367-10f4-481a-bab8-a540eab3f7a2.png)

## 풀이

```javascript
/*
  [programmers / 옷가게 할인받기]

  입출력 예
  price	result
  150,000	142,500
  580,000	464,000
*/

function solution(price) {
  let result;

  if (price >= 500000) result = price - price * 0.2;
  else if (price >= 300000) result = price - price * 0.1;
  else if (price >= 100000) result = price - price * 0.05;
  else result = price;
  return result;
}
```

먼저 걸려야하는 50만원 > 30만원 > 10만원 순으로 if 조건문을 걸어주어 계산을 진행하였음.

![image](https://user-images.githubusercontent.com/67165016/235187155-11cfbb85-c713-49a4-82c6-3982fefd2894.png)
음?... 뭐지 뭐가 문제일까....?

`아 잘보니까 제안사항에 소수점 이하를 버린 정수를 return합니다.` 라고 적혀있었음.

그래서 테스트 중에 소수점으로 나오는 것들이 있어 실패를 한 것 같다.

그래서 return할 때 정수로 반환해주기 위해 `parseInt()`를 덧붙였다.

![image](https://user-images.githubusercontent.com/67165016/235188256-85294432-2c97-493a-ba9b-8ecd8bb57e5a.png)

> 완료 ✅
