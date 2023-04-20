+++
author = "우명규"
title = "[Programmers] 분수의 덧셈 문제"
date = "2023-04-20"
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

![image](https://user-images.githubusercontent.com/67165016/233359762-135527e1-4c1d-45b4-8aba-f285e5e96423.png)

## 풀이

그냥 머리로 분수 덧셈하는건 해봤는데 이 공식을 코드로 직접 적어본다고 생각하니 조금 어려웠다.. 초등학교 문제인데..

적잖은 충격을 먹고나서 분수의 덧셈 공식을 다시 검색해봤다

그렇다 통분을 하고 기약분수로 나타내면 되었다고 생각했다.

```javascript
/*
  [programmers / 분수의 덧셈]

  입출력 예
  numer1 denom1	numer2	denom2	result
  1	2	3	4	[5, 4]
  9	2	1	3	[29, 6]
*/

function calculation(numer1, denom1, numer2, denom2) {
  //최대로 약분할 수 있는 숫자
  let max = 1;

  let numer = numer1 * denom2 + numer2 * denom1;
  let denom = denom1 * denom2;

  for (let i = 1; i < numer; i++) {
    if (denom % i === 0 && numer % i === 0) {
      max = i;
    }
  }

  return [numer / max, denom / max];
}

function solution(numer1, denom1, numer2, denom2) {
  var answer = calculation(numer1, denom1, numer2, denom2);
  return answer;
}
```

![image](https://user-images.githubusercontent.com/67165016/233358867-0c905a99-41d9-4bc4-a256-cd5daaf194d7.png)

음?.... 중간에 실패한 테스트 케이스가 있었다.

한가지 알아본 테스트 중 입력이 1, 2, 1, 2가 들어가게 되면 [1, 1]로 되어야하는데 [2, 2]로까지밖에 약분이 안되어있었다.

for문을 다시 확인해보니 `i <= numer`까지의 범위를 해줬어야했는데 `i < numer`까지 밖에 안한 것.

```javascript
/*
  [programmers / 분수의 덧셈]

  입출력 예
  numer1 denom1	numer2	denom2	result
  1	2	3	4	[5, 4]
  9	2	1	3	[29, 6]
*/

function calculation(numer1, denom1, numer2, denom2) {
  //최대로 약분할 수 있는 숫자
  let max = 1;

  let numer = numer1 * denom2 + numer2 * denom1;
  let denom = denom1 * denom2;

  for (let i = 1; i <= numer; i++) {
    if (denom % i === 0 && numer % i === 0) {
      max = i;
    }
  }

  return [numer / max, denom / max];
}

function solution(numer1, denom1, numer2, denom2) {
  var answer = calculation(numer1, denom1, numer2, denom2);
  return answer;
}
```

![image](https://user-images.githubusercontent.com/67165016/233360548-e9a3ee17-dd3f-424a-bce0-af6e58ecaccb.png)

> 완료 ✅
