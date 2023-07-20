+++
author = "우명규"
title = "[Programmers] 각도기"
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

![image](https://github.com/myeongcode/blog/assets/67165016/ca9fcaf1-56ca-40f6-a30d-e563d7fe3f99)

## 풀이

```javascript
/*
  [programmers / 각도기]

  angle	result
  70	1
  91	3
  180	4
*/

function solution(angle) {
  const angleResult = angle / 90;
  let answer;
  if (angleResult < 1) answer = 1;
  else if (angleResult === 1) answer = 2;
  else if (angleResult < 2) answer = 3;
  else answer = 4;

  return answer;
}
```

더 간단하게 코드를 줄일 수 있을 것 같은데.. 뭔가 아쉽다... 다른 사람들은 어떻게했을까?

[다른사람의 풀이]

```javascript
function solution(angle) {
  return [0, 90, 91, 180].filter((x) => angle >= x).length;
}
```

와,,,, 이렇게 하는 사람도 있네 미쳤다

어쨋든 뭐,,, 정답!

![image](https://github.com/myeongcode/blog/assets/67165016/d7716cc2-f44c-40aa-8255-ed4cfb76fb55)

> 완료 ✅
