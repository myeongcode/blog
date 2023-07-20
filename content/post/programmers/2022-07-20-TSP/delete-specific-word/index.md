+++
author = "우명규"
title = "[Programmers] 특정 문자 제거하기"
date = "2023-07-20"
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

![image](https://github.com/myeongcode/blog/assets/67165016/9b0bf011-37e2-4c14-b8a4-0976e356b496)

## 풀이

```javascript
/*
  [programmers / 특정 문자 제거하기]

  my_string	letter	result
  "abcdef"	"f"	"abcde"
  "BCBdbe"	"B"	"Cdbe"
*/

function solution(my_string, letter) {
  let regex = new RegExp(letter, "g");
  const answer = my_string.replace(regex, "");

  return answer;
}
```

replace를 바로 사용하면 되겠지? 하고 사용했는데 my_string이 "BCBdbe"가 되었을 때가 문제였다.

B가 총 두번나오는데 replace를 바로 하게된다면, 맨 처음 B만 제거되고 그 이후의 B는 제거되지 않는다.
즉, CBdbe라는 값으로 결과가 나왔다.

근데 또, 정규표현식으로 사용해볼려해도 `my_string.replace(/letter/g, "");` 가 바로 적용되지 않았다

왜냐하면 letter는 매개변수인데 매개변수로 읽히지않고, 'letter'라는 문자열을 찾으라는 뜻으로 해석되었기 때문

그래서 찾았는데 정규표현식 객체 생성사를 이용해서 패턴을 정의했다.
변하지 않는 특정 문자열을 찾을 때에는 그냥 `my_string.replace(/B/g, "");`처럼 사용하면 되지만, 변할 수 있는 문자열을 찾을 때에는 아래처럼 정규표현식 객체 생성자를 이용해서 제거하면 된다.

```javascript
let pattern = "Abc";
let text = "abcabaAbcabbbcAbc";

let regexOne = new RegExp(pattern); // 일치하는 패턴 중 최초 등장하는 패턴 한 번만 찾음
let regexAll = new RegExp(pattern, "g"); // 모든 패턴을 찾음
let regexAllCase = new RegExp(pattern, "gi"); // 대소문자 구분 없이 모든 패턴을 찾음

console.log(text.replace(regexOne, "___")); // abcaba___abbbcAbc
console.log(text.replace(regexAll, "___")); // abcaba___abbbc___
console.log(text.replace(regexAllCase, "___")); // ___aba___abbbc___
console.log(text); // abcabaAbcabbbcAbc
```

![image](https://github.com/myeongcode/blog/assets/67165016/f973c1ba-a9e8-4fab-8246-9cdacbe42b12)

> 완료 ✅
