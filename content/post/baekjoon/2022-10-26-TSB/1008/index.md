+++
author = "우명규"
title = "[Baekjoon] 1008번 문제"
date = "2022-10-26"
description = "백준 알고리즘"
tags = [
    "c",
]
categories = [
    "Baekjoon",
]
image = "baekjoon.png"
+++

<!--more-->

## 문제

![image](https://user-images.githubusercontent.com/67165016/232452717-70b27c10-305e-4c22-99c8-9cde609ed190.png)

## 풀이

(처음 생각한 답)

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main(void) {
    float a, b, result;

    scanf("%f %f", &a, &b);

    result = a / b;

    printf("%.10f", result);

    return 0;
}
```

하지만, 위의 문제에서 출력부분을 보면 **‘실제 정답과 출력값의 절대오차 또는 상대오차가 $10^{-9}$이하이면 정답’** 이라고 표시되어 있다.

이게 무슨말이냐?

먼저 float으로 받아서 float으로 출력을 해보면 다음과 같이 나옵니다.

![image](https://user-images.githubusercontent.com/67165016/232453481-95d37219-2c6b-4ac5-835b-82e3cd6d0fb4.png)

실제 답은 0.333333333333…이 나와야하는데 0.3333333433이 출력이 됩니다.

그러면 실제 답과의 절대오차는 0.0000000100…이 됩니다.

절대오차가 1 \* 10^{-8}만큼 차이나므로 10^{-9}이하가 아니게 됩니다

1 \* 10^{-8} > 10^{-9}

그러면 상대오차로 계산해보겠습니다.

상대오차는 배율로 생각하면 편합니다. 원래 답과의 차이가 +-10까지 허용한다 그러면 상대오차는 10^{-1}까지 허용하는 셈입니다. +-1까지 허용한다하면 10^{-2}까지 허용하는겁니다.

그렇다면, 0.3333333333과 0.3333333433의 상대오차는 어떻게 될까요

공식을 이용하면

![image](https://user-images.githubusercontent.com/67165016/232455500-e6f8e6cf-296c-4ccd-ae2e-b6f573245746.png)

상대오차 = {1*10^{-8}}{0.3333333333} * 100 = 0.000003

배율만큼 차이가 난다는 의미입니다. 그러므로 상대오차 또한 10^{-9}보다 크므로 상대오차도 오답이 되는 것입니다.

그러면 어떻게 해야하냐면 정밀도가 더 큰 자료형으로 바꾸면 됩니다.

float보다는 double의 정밀도가 더 큽니다.

float과 double의 범위또한 다르며 유효자릿수가 double이 더 크기때문에 더 정밀하다는 의미가 됩니다.

![image](https://user-images.githubusercontent.com/67165016/232455950-d3d9f822-11cd-4332-bc29-152afe40577b.png)

따라서, 백준에서는 더 정밀한 값을 정답으로 처리하겠다는 것입니다.

그럼 자료형을 float이 아닌 double로 바꿔서 출력해보겠습니다

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>


int main(void) {
    double a, b, result;
    printf("-------input-------\n");
    scanf("%lf %lf", &a, &b);

    printf("\n");
    result = a / b;
    printf("-------output-------\n");
    printf("%.10lf\n", result);

    return 0;
}
```

![image](https://user-images.githubusercontent.com/67165016/232456300-b76a620b-ba95-43a4-ab62-a5b8e049b76d.png)

![image](https://user-images.githubusercontent.com/67165016/232456359-4c6d3aba-5747-4dcc-8a76-7164384021b4.png)
