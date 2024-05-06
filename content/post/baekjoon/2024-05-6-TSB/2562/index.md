+++
author = "우명규"
title = "[Baekjoon] 2675번 문제"
date = "2024-05-06"
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

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/47f6c2e9-8ab8-418c-8174-569607a863ff)

## 풀이

처음에 문자열 S를 입력받아서 테스트케이스로 사용하게끔 만들고, 각 문자를 R번 반복하는 새 문자열 P를 만든 후 출력하는 프로그램이다.

첫 번째 문자는 반복할 개수, 두 번째 문자는 반복한 문자열을 입력받고, for문에서 각 인덱스의 값을 가져와서 사용하도록 작성했다.

그리고 for문 안에 또 for문을 통해 문자열을 각 문자로 쪼개서 문자 하나하나마다 반복할 개수만큼 곱해서 값을 더해주는 것으로 코드를 작성했다.

```python
# 테스트 케이스 개수 입력받기
testCaseCnt = int(input())

# 테스트 케이스 개수만큼 입력받기
inputData = [input().split() for _ in range(testCaseCnt)]

# 입력한 테스트케이스의 개수만큼 for문
for item in inputData:
  # 합칠 텍스트 변수 초기화
  string = ""
  # 입력한 값에서 첫 번째 문자는 반복 숫자로 가져오기
  number = int(item[0])
  # 입력한 값에서 두 번째 문자는 반복할 텍스트 가져오기
  text = item[1]

  # 해당 문자열의 개수만큼 for문으로 반복
  for char in text:
    # 문자열의 각 문자는 char이 되고 해당 텍스트를 number만큼 표시해서 string에 넣어주기
    string += char*number

  print(string)
```

성공은 했지만, 성공 후 다른 사람들이 푼 python코드를 살펴보던 와중에 참고하면 좋을 코드가 있어 가져와봤다.

```python
n = int(input())
for _ in range(n):
    # 여기에서 굳이 인덱스로 쪼개지 않고도 split을 해서 나온 첫 번째 문자와 두 번째 문자의 결과를 각각 cnt와 word에 저장시켜 줄 수 있다.
    cnt, word = input().split()
    for x in word:
        print(x*int(cnt), end='')  # end='' 옆으로 붙임
    print()  # 줄넘김
```

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/bf5ddb03-8f50-416d-adf3-a06c91cca8d2)

> 해결완료 ✅
