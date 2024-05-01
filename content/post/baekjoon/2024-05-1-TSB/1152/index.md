+++
author = "우명규"
title = "[Baekjoon] 1152번 문제"
date = "2024-05-01"
description = "백준 알고리즘"
tags = [
    "python",
]
categories = [
    "Algorithm",
]
image = 'baekjoon.png'
+++

<!--more-->

## 문제

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/0d0f077c-5daf-463c-87c7-142d7e6e041d)

## 풀이

주로 자바스크립트만으로 알고리즘 문제를 진행해보다가 이제는 파이썬으로 알고리즘 문제를 해결하려고 한다.

그렇기에 기초문제부터 차근차근 하면서 파이썬 문법과 사용법을 알아 갈 예정이다!

가볍게 1152번 문제를 풀어봤고, 어떤 입력을 받으면 그 입력의 단어들의 개수를 출력해주는 것이였다.
자바스크립트에서의 `.slice()`나 `.split()`을 통해 단어들을 자르고 그 단어들의 개수를 출력해주면 되지 않을까 생각했고 파이썬에서도 단어들을 잘라주는 함수가 있는지 구글링을 한 결과 JS와 똑같이 `.split()`함수가 존재했었다.

그래서 입력받은 값을 공백을 기준으로 split해주면 해당 단어들이 리스트(?)로 표시되는데 이 리스트들의 값만 출력해주면 돼서 쉽게 출 수 있었다.

참고로 파이썬에서 개수를 표시하는 방법은 `len()`함수를 사용한다고 한다.

```python
inputData = input()

print(len(inputData.split()))
```

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/0093e56d-0f4b-40c9-a41f-4a83fbfe7439)

> 해결완료 ✅
