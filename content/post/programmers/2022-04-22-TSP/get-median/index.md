+++
author = "우명규"
title = "[Programmers] 중앙값 구하기 문제"
date = "2023-04-22"
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

![image](https://user-images.githubusercontent.com/67165016/233772785-62a42623-d1e4-40b4-a21b-551b0f2cddbf.png)

## 풀이

```javascript
/*
  [programmers / 중앙값 구하기]

  입출력 예
        array	        result
  [1, 2, 7, 10, 11]	  7
  [9, -1, 0]	          0
*/

function solution(array) {
  let sort_array = array.sort((a, b) => {
    if (a > b) return 1;
    if (a === b) return 0;
    if (a < b) return -1;
  });
  let half_array = parseInt(sort_array.length / 2);

  let answer = sort_array[half_array];
  return answer;
}
```

그냥 sort로 정렬을 하게되면 유니코드 순서에 따라서 값을 정렬하게 되므로 만약, [1, 2, 7, 10, 11]을 `sort()` 하게되면 [1, 10, 11, 2, 7]로 정렬이 됩니다.

그래서 우리는 파라미터를 사용해서 a, b 두 개의 파라미터를 입력받고 a > b이면 1을, a === b면 0을, a > b이면 -1을 리턴해서 숫자 크기대로 정렬하게 해주었습니다.

![image](https://user-images.githubusercontent.com/67165016/233773559-f764858b-b7ca-4386-8833-8e9e14e5a3c4.png)

> 완료 ✅
