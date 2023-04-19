+++
author = "우명규"
title = "[Baekjoon] 10757번 문제"
date = "2023-04-19"
description = "백준 알고리즘"
tags = [
    "javascript",
]
categories = [
    "Baekjoon",
]
image = 'baekjoon.png'
+++

<!--more-->

## 문제

![image](https://user-images.githubusercontent.com/67165016/233016809-15c8507d-825b-4984-9207-d5f81291ee52.png)

## 풀이

```javascript
/*
  [baekjoon / 10757]

  9223372036854775807 9223372036854775808
*/

const fs = require("fs");
let input = fs.readFileSync("./input.txt").toString();
let result = input.split(" ").filter((num) => num !== "");
let num1 = parseInt(result[0]);
let num2 = parseInt(result[1]);

solution(num1, num2);

function solution(param1, param2) {
  console.log(param1 + param2);
}
```

처음엔 쉽게 정답이 될 줄 알았다..

근데 자꾸 이상한 답이 나오더라?

![image](https://user-images.githubusercontent.com/67165016/233047039-9e91cae3-2d85-4f96-9749-9967a24ec4f6.png)

음?.... 뭐야 분명 `18446744073709551615`이란 값이 나와야하는데 계속 `18446744073709552000`이 나옴

아ㅋㅋ

결국 한개씩 출력해봄 입력도 이상하게 나오는지

![image](https://user-images.githubusercontent.com/67165016/233047556-f7da36a6-523b-4656-be58-f2e04b9aaeeb.png)

음? ㅋㅋ 이건 또 뭐임

찾아보니 Javascript에는 BigInt라는 새로운 데이터형이 존재한다는 것을 알았다. BigInt는 **Javascript Number의 최대범위인 2^53 - 1보다 큰 정수를 표현**할 수 있다고 한다.

[Javascript BigInt](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt)

그래서 `parseInt()`대신 `BigInt()`로 바꿔서 출력해봤다.

```javascript
...
let num1 = BigInt(result[0]);
let num2 = BigInt(result[1]);
...
```

![image](https://user-images.githubusercontent.com/67165016/233049643-cdc3f078-65e3-4e35-94d9-789c929c1fad.png)

드디어 숫자가 변하지 않고 정확하게 출력되는 것을 볼 수 있다. 근데, 뒤에 n이라는 문자가 같이 표기되어 나온다?

이건 `.toString()` 메소드를 쓰면 해결되었다.

![image](https://user-images.githubusercontent.com/67165016/233051533-fddd9f7f-f689-4237-bb41-9efd3e6f99e5.png)

^오^

다시 두 수의 덧셈을 구하여 출력해보는 걸로 하고, 백준의 입력을 받을 수 있게끔 읽는 파일을 `"/dev/stdin"`으로 바꿔주자

```javascript
/*
  [baekjoon / 10757]

  9223372036854775807 9223372036854775808
*/

const fs = require("fs");
let input = fs.readFileSync("/dev/stdin").toString();
let result = input.split(" ").filter((num) => num !== "");
let num1 = BigInt(result[0]);
let num2 = BigInt(result[1]);

solution(num1, num2);

function solution(param1, param2) {
  let result = param1 + param2;
  console.log(result.toString());
}
```

![image](https://user-images.githubusercontent.com/67165016/233051908-b5a86586-9504-4bab-8263-009383641d21.png)

![image](https://user-images.githubusercontent.com/67165016/233053742-c3c773d3-3ee6-4c42-9eda-5ec3fe59220a.png)

> 해결완료 ✅
