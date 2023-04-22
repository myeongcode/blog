+++
author = "우명규"
title = "[Programmers] 최빈값 구하기 문제"
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

![image](https://user-images.githubusercontent.com/67165016/233773664-04a34d03-ae66-4df4-a342-64b10bcada96.png)

## 풀이

음.... 이걸 어떻게 코드로 표현할까 고민을 많이 하던 중 그냥 어떤 식으로 하면될지 그려봤습니다.

![image](https://user-images.githubusercontent.com/67165016/233777299-e6466fb3-d110-4c3d-b996-0c51aaa0fcf1.png)

나는 이런 방식으로 문제를 해결해볼려고 그랬지만, 이게 완전 최적의 코드라고는 장담을 못했습니다.

아무튼 그래서 내가 작성한 코드는 다음과 같습니다.

```javascript
/*
  [programmers / 최빈값 구하기]

  입출력 예
  array	result
  [1, 2, 3, 3, 3, 4]	3
  [1, 1, 2, 2]	-1
  [1]	1
*/

function solution(array) {
  let arrayObject = [];
  let maxLength = 0;
  let maxNum = 0;

  for (var i = 0; i < array.length; i++) {
    if (arrayObject.find((e) => e.name === array[i])) {
      arrayObject.find((e) => e.name === array[i]).array.push(array[i]);
    } else {
      let newObject = { name: array[i], array: [array[i]] };
      arrayObject.push(newObject);
    }
  }

  arrayObject.map((data, index) => {
    if (maxLength < data.array.length) {
      maxLength = data.array.length;
      maxNum = data.name;
    } else if (maxLength === data.array.length) {
      maxNum = -1;
    }
  });

  return maxNum;
}
```

arrayObject라는 객체를 만들고 인자로 받은 array를 for문으로 돌려 만약 저 객체에 1이라는 원소가 없으면 name은 해당 원소오 하고 array로 해당 원소가 얼만큼 있는지 배열로 나타내는 새로운 객체를 생성해서 arrayObject에 push를 해줬습니다.

그리고 1이라는 원소가 있으면 해당 객체의 array의 key값에 해당 원소를 push해줘서 배열이 쌓일 수 있도록 만들었습니다.

![image](https://user-images.githubusercontent.com/67165016/233777699-caa5775a-f66a-4a25-a81a-16822a5ea3b5.png)

그리고는 만들어진 객체에서 비교를 진행합니다. `maxLength`와 `maxNum`을 만들고 map함수를 이용해서 새로운 객체의 배열값이 더 높을때만 `maxLength`와 `maxNum`을 업데이트해주고 만약 최빈값의 개수가 같은 객체가 있다면 바로 `maxNum`에 -1을 넣어주었습니다.

그 결과 다음과 같이 결과를 얻을 수 있었습니다.

![image](https://user-images.githubusercontent.com/67165016/233777725-3f47280f-390a-4284-8557-f9b5e6b9489f.png)

![image](https://user-images.githubusercontent.com/67165016/233777758-d9876921-8b0a-44b7-8d49-8f00629025f4.png)

> 완료 ✅
