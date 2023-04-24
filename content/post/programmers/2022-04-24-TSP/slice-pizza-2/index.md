+++
author = "우명규"
title = "[Programmers] 피자 나눠먹기 - 2"
date = "2023-04-24"
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

![image](https://user-images.githubusercontent.com/67165016/233985083-1fac9e41-a005-415a-beee-3b8df17971f2.png)

## 풀이

```javascript
/*
  [programmers / 피자 나눠먹기 - 2]

  입출력 예
  n	result
  6	1
  10	5
  4	2
*/

function gcd(a, b) {
  let result;

  while (b != 0) {
    result = a % b;
    a = b;
    b = result;
  }
  return a;
}

function solution(n) {
  let defaultSlice = 6;
  let person = n;
  let lcm;

  if (person < defaultSlice) {
    lcm = (person * defaultSlice) / gcd(defaultSlice, person);
    return lcm / 6;
  } else {
    lcm = (person * defaultSlice) / gcd(person, defaultSlice);
    return lcm / 6;
  }
}
```

이 문제는 보자마자 최소공배수를 구하면 되겠구나 하는 생각이 먼저들었음.

그래서 최소 공배수를 구하기 위해 먼저 최대공약수를 구하기 위해 `gcd(a, b)`를 만들어서 그 결과를 return했고, `최소공배수 = 두 수의 곱 / 최대공약수`이므로 그 값을 피자 조각인 6으로 나누어 피자의 개수를 return하였다.

사실 최소공배수를 어떻게 구하지 막막했는데 '최소공배수를 구하는 법'을 치니까 [유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)이라는 것이 언급되었다.

## 유클리드 호제법

유클리드 호제법은 2개의 자연수의 최대공약수를 구하는 알고리즘의 하나이고, 두 수가 서로 상대방 수를 나누어서 결국 원하는 수를 얻는 알고리즘이다.

2개의 자연수 a, b에 대해서 a를 b로 나눈 나머지를 r이라 하면(단, a > b), a와 b의 최대 공약수는 b와 r의 최대공약수와 같다.

좀, 말이 어려울 수도 있는데 간단히 말하자면

> a를 b로 나눈 나머지를 r이라 했고, 또 b를 r로 나눈 나눈 나머지를 r'이라 하고, 또 r을 r'로 나눈 나머지를 r'' 이런식으로 과정을 반복해서 나머지가 0이 되었을 때 마지막으로 나누는 수가 `최대공약수`가 되는 것이다.

### 계산 예

만약 a가 24, b가 18이라고 해보자

|     | GCD         | a   | b   | a % b |
| --- | ----------- | --- | --- | ----- |
| 1회 | GCD(24, 18) | 24  | 18  | 6     |
| 2회 | GCD(18, 6)  | 18  | 6   | 0     |

2번째 시도만에 나머지가 0으로 떨어졌으며, 결국 **마지막에 나누는 수(6)이 최대공약수가 되는 것**이다.

그래서 이것을 코드로 작성한 것이 `gcd(a, b)`에 해당이 되는 것이고, 최대공약수를 알면 최소공배수는 바로 구할 수 있다.

`최소공배수 = 두 수의 곱 / 최대공약수`

그리고 마지막으로 피자의 조각이 아닌 피자의 개수를 구하는 것이므로 6조각 당 1개이므로 6으로 나눈 몫을 return하여 피자의 개수를 구하였다.

![image](https://user-images.githubusercontent.com/67165016/233996001-8bd3bc58-897b-4e67-a6df-4cd8fdc2f9ec.png)

> 완료 ✅
