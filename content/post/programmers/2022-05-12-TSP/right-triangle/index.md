+++
author = "우명규"
title = "[Programmers] 직각삼각형 출력하기"
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

![image](https://github.com/myeongcode/blog/assets/67165016/32c457b0-dd1b-43f3-904f-bc9cef4bd280)

## 풀이

```javascript
/*
  [programmers / 직각삼각형 출력하기]

  입력 #1

  3

  출력 #1

  *
  **
  ***
*/

const readline = require("readline");
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

let input = [];

rl.on("line", function (line) {
  input = line.split(" ");
}).on("close", function () {
  for (let i = 0; i < Number(input); i++) {
    console.log("*".repeat(i + 1));
  }
});
```

readline을 처음보고 벙쪘다.. 이게 무슨 코드인지 몰라서..

### readline이란?

> Readable Stream에서 한 번에 한 줄씩 데이터를 읽기 위한 인터페이스를 제공하는 모듈

즉, 입출력을 처리하게해주는 JS 내장 모듈입니다.

### readline 사용법

#### 모듈 불러오기

```javascript
const readline = require("readline");
```

#### interface 객체 만들기

interface 객체를 이용하여 콘솔에서 표준 입출력 처리를 할 수 있습니다.

```javascript
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});
```

- stdin : standard input
- stdout : standard output

#### 입출력 코드 작성하기

```javascript
rl.on("line", (line) => {
  // 입력 받은 값을 처리하는 코드
  rl.close();
});

rl.on("close", () => {
  // 입력이 끝나고 실행하는 코드
  process.exit();
});
```

- `on()` : 메서드를 활영하여 이벤트와 콜백함수를 전달
- `'line'` : 입력받은 값을 한 줄씩 읽어 문자열 타입으로 전달하는 역학을 하는 이벤트.
- `rl.close()` : 인터페이스를 종료. 무한히 입력 받는 것을 방지하며, close를 작성하여 입력이 끝난 후 실행되어야 할 함수를 작성합니다.

---

아무튼 readline은 아래에 조금 더 내용을 참조하였고, 우리는 3을 입력받았으므로 직각삼각형 모양으로 별을 출력해줘야한다.

그러기위해서는 반복되어야하는 for문을 사용했고, 출력될 때 `repeat()`를 사용하여 for문을 반복한 만큼 \*을 찍게했다.

근데 여기서 별이 처음부터 찍혀야하니 repeat(i+1)을 해주었다.

![image](https://github.com/myeongcode/blog/assets/67165016/22b51e01-0989-48a2-ae14-53af31eaf65e)

> 완료 ✅
