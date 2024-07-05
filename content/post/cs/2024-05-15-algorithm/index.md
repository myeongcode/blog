+++
author = "우명규"
title = "알고리즘의 개념 & 시간복잡도"
date = "2024-05-15"
description = "알고리즘이 무엇인지 성능에서 중요시하는 시간복잡도에 대하여 정리해보자"
tags = [
    "computer science",
]
categories = [
    "CS",
]
image = 'algo.png'
+++

<!--more-->

## 개요

우리는 코딩을 하면서 알고리즘이라는 것을 흔하게 마주하고 개발자라면 피할 수 없는 개념이 바로 `알고리즘`이다.

그렇다면, 알고리즘이 뭔지 왜 우리가 알고리즘을 알고 사용해야하는지를 알아야 합니다. 학교에서 알고리즘에 대한 내용들을 배우면서 tree, stack, queue등 다양한 자료구조가 있는지를 공부했다. 하지만, 이 알고리즘이라는 것을 사용하는 이유에 대해 설명하라고 한다면, 순간 뇌정지가 오며 어버버 할 가능성 100%

그래서.. 알고리즘에 대해서 나만의 방식으로 정리하고 누군가가 물어봤을 때에도 이해를 잘 시켜줄 수 있을만큼 정리를 하려한다.

## 알고리즘?

우리는 알고리즘이 탄생하게 된 이유를 알아야 한다.

살다보면 어떠한 문제를 앞에 놓고 막연하게 어떻게 해결해야 하는지에 대해 고민을 해야할 때가 있다. 그럴 때 우리는 문제들을 해결하기 위한 여러 동작을 하게되는데 이것들을 수학적으로 계산하여 추론하기 위한 ‘일련의 단계적 절차’이자 ‘동작들의 모임’이라고 한다.

즉, `알고리즘`이란 **문제점을 해결하기 위한 방법과 절차**이다.

예를 들어, 학생 100명의 시험 점수의 평균을 내야한다고 했을 때 당신이라면 어떻게 해결하겠습니까?

물론 100명의 시험 점수를 모두 더해서 100으로 나누면 되겠지만.. 1000명, 1만명의 시험 점수를 평균 내야한다고 했을 때에도 똑같은 방법으로 할 수 있을까? 아마 시간과 효율이 많이 떨어지게 될 것이다.

그래서 우리는 이런 문제를 해결할 때는 시간과 효율성을 중요하게 생각해야 한다.

특히나 어떤 입력을 받고 연산을 처리하여 결과를 출력해야하는 개발자에게는 더욱 더 시간과 효율이 중요하기에 <u>알고리즘이라는 해결 과정을 통해 효율적으로 결과를 만들어 내는 것</u>

그래서 이런 해결 과정을 어떻게 설계 할건지에 따라 시간과 효율이 나누어지게 된다.

우선 우리는 알고리즘을 설계하기 위해서는 해야 할 작업을 명확하게 명시해야한다.<br/>
즉, 설계하려는 알고리즘이 `무엇을` 하는지 `입력`과 `출력`으로 명시할 수 있다.
![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/2caec0af-38d0-4ec4-ad63-50b8644328f7)
알고리즘에서 우리가 따져봐야하는건 이 알고리즘의 **효율성**, **명확성**이다

이 효율성을 평가하기 위해 알고리즘의 성능을 나타내는 척도로는 크게 **공간복잡도(space complexity)**, **시간복잡도(time complexity)** 로 나타낼 수 있다.<br/>
즉, `어떤 알고리즘이 효율적인지를 판단하는 척도`

- **공간복잡도(space complexity)** : 프로그램 실행과 완료에 얼마나 많은 공간(메모리)가 필요한지에 대한 지표
- **시간복잡도(time complexity)** : 프로그램 완료에 얼마나 빠르게 실행(얼마나 많이 연산)되는지에 대한 지표<br/>
  즉, **특정 크기의 입력을 기준으로 할 때 필요한 연산의 횟수**

<u>보통은 시간복잡도를 위주로 알고리즘의 성능을 판단</u>하기에 시간 복잡도에 대해서 자세히 알아야한다.

## 시간복잡도 (Time complexity)

⇒ 시간복잡도는 `연산 횟수`를 세는 것

_\*왜 시간복잡도라고 말하면서 실행 시간이 아니라 연산 횟수를 세는 것일까?_<br/>
⇒ 모든 OS, IDE, 플랫폼에서 동일한 결과가 나오지 않기 때문에 연산 횟수로 사용

하지만, 이렇게 연산 횟수도 어떤 경우인지에 따라 시간 복잡도가 나뉘어진다.<br/>
경우는 아래와 같이 3가지로 나뉜다.

- <span style="color:#5A8DFF;">**최선의 경우 (Best Case)**</span><br/>
  ⇒ 최적의 입력을 한 상태에서, 작업을 완료하는 데 가장 연산 횟수가 적은 경우
- <span style="color:#FF4343;">**최악의 경우 (Worst Case)**</span><br/>
  ⇒ 최악의 입력 한 상태에서, 작업을 완료하는 데 가장 연산 횟수가 많은 경우
- <span style="color:#FF8C35;">**평균의 경우 (Average Case)**</span><br/>
  ⇒ 여러 경우의 수를 고려하여, 총 연산 횟수를 계산하고 시행 횟수로 나눈 경우

알고리즘 분석 시 평균의 경우와 최악의 경우가 가장 많이 활용되며, 알고리즘이 복잡해질수록 평균을 구하기 어려워져 <u>최악의 경우로 알고리즘 성능을 파악</u>한다.

예시를 통해 시간 복잡도에 대해 알아봅시다.

```python
algorithm ArrayMax(A,n):
    currentMax = A[0]············(ㄱ)
    for i = 1 to n-1 do···········(ㄴ)
        if currentMax < A[i]:········(ㄷ)
            currentMax = A[i]········(ㄹ)
    return currentMax
```

위와 같은 배열 A에서 최대값을 리턴하는 알고리즘이 있을 때, 입력값과 출력값은 아래와 같다.

- 입력값 : n개의 정수를 갖는 배열 A
- 출력값 : A의 수 중에서 가장 큰 값

출력값은 어쨋든 A 중에서 가장 큰 값을 출력해주면 됩니다. <br/>
반면, 입력값은 어떤 것이 들어올지 알 수 없습니다.

- 몇 개의 정수를 가진 배열이 입력될지
- 배열A의 숫자는 어떤 것이 들어갈지
- 어떤 정수의 숫자 n이 들어올지

예상할 수 없습니다.

그렇기에 어떤 입력이 들어와도 이 WTC(Worctcase Time Complexity)보단 수행 시간이 적기때문에 WTC로 최대로 연산했을 때의 시간복잡도를 측정할 수 있습니다.<br/>
여기서 만약 A=[4, 3, 2, 1, …]과 같이 계속 줄어들게 된다면 0번째 인덱스가 가장 크기때문에 (ㄹ)번 문장을 실행하지 않게 됩니다.<br/>
하지만, A=[1, 2, 3, 4, …]과 같이 계속 증가하는 숫자가 있다고 한다면 <u>(ㄹ)번 문장을 계속해서 실행해야 합니다. (ㄹ)번 문장을 실행한다는 것은 대입 연산을 한번 더 해야하고 알고리즘 수행 시간이 증가</u>하게 됩니다.

모든 입력값에 대한 시간복잡도는 일반적으로 <span style="color:#FF4343;">**T(n)**</span>으로 표기합니다.

예를들어, n=5이고 A=[3, -1, 9, 2, 12]라고 가정해보자.

(ㄱ) A[0]의 값 3은 currentMax에 저장이 되면서 <span style="color:#FF4343;">**대입연산**</span>을 합니다. (1회)

(ㄴ) 반복문을 실행합니다.

1. A[1]과의 비교

   (ㄷ) 현재 currentMax에 저장되어있는 값 3이 A[1]의 값 -1보다 작은지 <span style="color:#FF4343;">**비교연산**</span>을 합니다 (2회)

   <span style="color:#808080;">비교 결과 currentMax의 값이 더 크므로 (ㄹ) 문장을 건너뛰게 됩니다.</span>

2. A[2]와의 비교

   (ㄷ) 현재 currentMax에 저장되어 있는 값 3이 A[2]의 값 9보다 작은지 <span style="color:#FF4343;">**비교연산**</span>을 합니다. (3회)

   (ㄹ) 비교 결과 A[2]의 값이 더 크므로 (ㄹ) 문장을 실행시키고 A[2]의 값인 9를 currentMax에 <span style="color:#FF4343;">**대입연산**</span>을 합니다. (4회)

3. A[3]와의 비교

   (ㄷ) 현재 currentMax에 저장되어 있는 값 9가 A[3]의 값 2보다 작은지 <span style="color:#FF4343;">**비교연산**</span>을 합니다. (5회)

   <span style="color:#808080;">비교 결과 currentMax의 값이 더 크므로 (ㄹ) 문장을 건너뛰게 됩니다.</span>

4. A[4]와의 비교

   (ㄷ) 현재 currentMax에 저장되어 있는 값 9가 A[4]의 값 12보다 작은지 <span style="color:#FF4343;">**비교연산**</span>을 합니다. (6회)

   (ㄹ) 비교 결과 A[4]의 값이 더 크므로 (ㄹ) 문장을 실행시키고 A[4]의 값인 12를 currentMax에 <span style="color:#FF4343;">**대입연산**</span>을 합니다. (7회)

이렇게 총 7회의 기본 연산을 진행하게 됩니다. (반복문 제외)<br/>
이렇게 연산을 할 때 안 할때에 따라 연산 횟수가 달라지게 되는데, 여기서 Worstcase의 경우면 (ㄹ)문장이 매 조건마다 실행되었을 때를 가정하는겁니다. 그래서 이때 Worstcase는 총 9번의 연산을 하게 되는겁니다.

반복문 안 (ㄷ), (ㄹ) 문장을 보면, (ㄷ)문장에서 비교 연산 1회, (ㄹ)문장에서 대입연산 1회를 실행합니다.<br/>
(ㄴ) 문장에서 for문은 1부터 n-1까지 총 n-1회 실행하게 됩니다.<br/>
따라서, (ㄷ), (ㄹ) 문장 2회 \* 반복문 n-1회 → 2(n-1) = 2n-2가 됩니다.<br/>
하지만 (ㄱ) 문장에서 대입연산도 1회 더해야하기 때문에 2n-2+1을 하게되면 시간복잡도는 총 <span style="color:#FF4343;">**T(n) = 2n-1**</span>이 됩니다.<br/>
그럼 n=100일 때의 시간복잡도(연산 횟수)를 손쉽게 구할 수 있습니다.<br/>
<span style="color:#808080;">_*n=100, T(100) = 2 * 100 - 1 = 199번의 연산 횟수를 갖게됨._</span>

### 예시1) sumEven함수의 시간 복잡도 구하기

배열A에서 짝수인 수 만을 더하는 함수의 시간복잡도 T(n)을 구해보자.

```python
algorithm sumEven(A,n):
    sum=0··············(ㄱ)
    for i=0 to n-1 do········(ㄴ)
        if A[i]%2 == 0:···· ··(ㄷ)
            sum+=A[i]········(ㄹ)
    return sum
```

해당 알고리즘에서 worst case는 (ㄹ)이 계속해서 실행되는 경우이다. 그러기 위해선 (ㄷ)의 조건이 항상 참이여야하므로 A[i]%2 == 0이 되려면 <u>A의 배열은 모두 짝수</u>여야한다.

A배열의 모든 값이 짝수라고 가정하면 수행시간은 다음과 같을 것이다.

- (ㄱ) 문장에서 대입연산 수행 (1회)<br/>
- (ㄴ) 반복문 0부터 n-1까지 n번 반복 (총 2회)<br/>
  - (ㄷ)에서 A[i]%2 (산술연산) 수행 (2회)<br/>
  - (ㄷ)에서 A[i]%2 == 0 (비교연산) 수행 (3회)<br/>
  - (ㄹ)에서 sum += A[i] → sum = sum + A[i] (총 2회)<br/>
    - (1) sum + A[i] (산술연산) 수행 (4회)<br/>
    - (2) sum = sum + A[i] (대입연산) 수행 (5회)<br/>

n번 진행하는 반복문 안에서 (ㄷ), (ㄹ) 문장을 연산 4회 진행하기 때문에 4n

(ㄱ)문장에서 1회 진행하므로 <span style="color:#FF4343;">**T(n) = 4n + 1**</span>이 된다.

### 예시2) 이중 for문의 sum2함수의 시간복잡도 구하기

```python
algorithm sum2(A,n):
    sum=0························(ㄱ)
    for i=0 to n-1 do············(ㄴ)
        for j=i to n-1 do········(ㄷ)
            sum+=A[i]*A[j]·······(ㄹ)
    return sum
```

이렇게 반복문이 바로 중첩되어 있는 경우라면, 첫 번째 반복문 i와 두 번째 반복문 j의 관계를 파악해야합니다.

| i   | j   |
| --- | --- |
| 0   | n   |
| 1   | n-1 |
| 2   | n-2 |
| …   | …   |
| n-1 | 1   |

(1) i=0일 때, j는 n번 반복<br/>
(2) i=1일 때, j는 n-1번 반복<br/>
(3) i=2일 때, j는 n-2번 반복<br/>
…<br/>
(n) i=n-1일 때, j는 1번 반복<br/>

그렇다면, j의 경우의 수를 모두 더하면 기본 연산이 있는 반복문이 몇 번 진행되는지 알 수 있습니다.<br/>
(ㄴ)는 n번 반복되고, (ㄷ)는 각 i에 대해 n-i번 반복되므로 전체 반복횟수는 다음과 같습니다.

$$
\sum_{i=0}^{n-1}(n-i)
$$

이므로, 이 합을 계산해보면

$$
\sum_{i=0}^{n-1}(n-i)=n+(n-1)+(n-2)+...+1
$$

가 됩니다.<br/>
이는 역수열의 합이고, 다음과 같이 계산할 수 있습니다.

$$
\sum_{k=1}^{n}k=\frac{n(n+1)}{2}
$$

따라서, 반복 연산은 $\frac{n(n+1)}{2}$ 번만큼 실행됩니다.

- (ㄱ) 대입 연산 수행 (1회)

- (ㄴ) 반복문 0부터 n번 수행

  - (ㄷ) i에 대해 n-i번 수행
  - (ㄹ) 문장

    - (1) A[i] **\*** A[j]의 산술연산 수행 (1회)

    - (2) sum **+** A[i] \* A[j]의 산술연산 수행 (1회)

    - (3) sum **=** sum + A[i] \* A[j]의 대입연산 수행 (1회)

반복문에서 $\frac{n(n+1)}{2}$ 회 반복을 진행하고 (ㄹ)문장에서 산술연산 2회 + 대입연산 1회 = 총 3회 연산을 진행하므로

$$
3\times\frac{n(n+1)}{2}
$$

(ㄱ)에서 대입 연산 1회를 수행하므로
$$3\times\frac{n(n+1)}{2} + 1$$
$$\frac{3n^2}{2}+\frac{3n}{2}+1$$
따라서 <span style="color:#FF4343;">**T(n)**</span>은 아래와 같이 시간복잡도를 표시한다.
$$T(n) = \frac{3n^2}{2}+\frac{3n}{2}+1$$

## BIG-O 표기법

⇒ 주어진 함수에서 <u>**가장 빨리 증가하는 항만을 남긴채 나머지를 다 버리는 표기법**</u>

우리는 위의 시간복잡도 $T(n)$을 통해 알고리즘의 수행시간<br/>
즉, 최악의 조건인 시간복잡도를 계산할 수 있게 되었습니다.

![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/55db2a5f-3c5d-420a-b17a-0a35b628eac5)
위의 시간복잡도의 증가율을 위와 같이 그래프로 표시하면 $n$의 증가율에 따라 변화하는 모습을 볼 수 있습니다.<br/>
여기서 ArrayMax과 sum1(sumEven)의 최고차항은 $n$입니다. 따라서 입력한 크기 n에 대하여 선형적으로 증가하는 모습을 확인할 수 있는 반면 sum2의 최고차항은 $n^2$이므로 n에 대하여 제곱으로 증가하는 모습을 확인할 수 있습니다.

여기서 우리는 <u>입력한 크기 n이 커질 때, 수행 시간이 얼마나 증가</u>하는지가 중요하다는 것을 알아야합니다.<br/>
즉, 입력값이 커질수록 **함수값의 증가율은 최고차항이 좌지우지**하기 때문에 상수항들은 알고리즘의 기본 연산 횟수에 큰 영향을 미치지 못합니다.

그래서 다른 것들은 다 신경쓰지 않고 최고차항만으로 시간복잡도의 대략적인 형태를 나타낸 것을 <span style="color:#FF4343;">**BIG-O표기법**</span>이라 합니다.<br/>
따라서, 시간 복잡도 $T(n)$을 BIG-O로 표기하게 된다면 다음과 같이 표기할 수 있다.
![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/07ed5b07-9cab-493c-b0b0-fc1ce1597e0c)
분명 다른 알고리즘의 시간복잡도가 다름에도 최고차항이 같기때문에 $O(n)$으로 동일합니다.

BIG-O 표기법은 <u>증가율 측면에서 표기하는 것이기 때문에 크게 보면 같은 알고리즘</u>이라고 할 수 있습니다.

_\*sum2의 시간복잡도는 $\frac{3n^2}{2}+\frac{3n}{2}+1$이므로 BIG-O는 $O(n^2)$이라고 표시할 수 있다._

---

```python
def increment_one(a):
    return a+1
```

위와 같은 알고리즘이 있다고 할 때, $T(n)=1$이다. 이런 경우에는 최고차항은 $n^0$이므로 BIG-O표기법으로 나타내면 $O(1)$입니다.

<span style="color:#808080;">\*_정말 1번만 한다는 의미가 아니라, 어떠한 입력이 들어와도 연산 횟수가 일정하면 $O(1)$과 같이 나타냅니다._</span>

---

```python
def number_of_bits(n):
    count=0
    while n>0:
        n=n//2
        count+=1
    return count
```

위와 같은 알고리즘이 있다고 할 때, 입력값 n이 들어오면 2로 나눈 몫을 n에 대입하는데, 몇 번 할 수 있는지 count해서 return하는 알고리즘이 있다.<br/>
예를 들어, n=8이라면 n은 반복문을 거칠 때 마다 8 → 4 → 2 → 1 → 0 순으로 바뀌고 count는 4를 반환할 것입니다. 또한 반복문 한 번 돌 때마다, n의 값은 $\frac{n}{2^1}$ → $\frac{n}{2^2}$ → $\frac{n}{2^3}$ →$\frac{n}{2^4}$ 순으로 바뀔 것 입니다.

결국은 $\frac{n}{2^{count}}$가 되어야 반복문이 끝나게 되는 것이므로 $\frac{n}{2^{count}}=1$이 됩니다.

> 1. 양변에 $2^{count}$를 곱하여 정리하면<br/> $n=2^{count}$
> 2. 이 식의 양변에 $\log_2$를 취하면<br/> $\log_2{(n)}=\log_2{(2^{count})}$
> 3. 로그의 성질을 이용해서 오른쪽 식을 풀어쓰면 <br/> $\log_2{(n)}=count\cdot\log_2{(2)}$
> 4. $\log_2{(2)}$는 1이므로 식은 다음과 같이 단순화됩니다.<br/> $\log_2{(n)}=count$

따라서, $\frac{n}{2^{count}}=1$을 n에 대해서 정리하면 $\log_{2}{(n)}=count$가 됩니다.

또한, while 반복문에서 n//2(산술연산) 1회, n=n//2(대입연산) 1회, count+1(산술연산) 1회, count=count+1(대입연산) 1회이므로 $4\times\log_2{(n)}$이고

count=0(대입연산)의 상수연산을 더하면 $4\times\log_2{(n)}+1$이 됩니다.

따라서, $T(n)=4\times\log_2{(n)}+1$이 되고, $O(\log_2n)$이 되며,
보통은 $O(\log n)$ 이렇게 쓴다

## BIG-O 실행 순서

⇒ 서로 다른 알고리즘의 시간복잡도의 BIG-O
![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/df9e8804-9ab4-4470-b6ae-09e8e03b86b2)
![image](https://github.com/myeongcode/myeongcode.github.io/assets/67165016/e1d6b6ca-3d47-490b-8ef0-73bb007be2d3)
다른 알고리즘이 궁금하다면 https://www.bigocheatsheet.com/

여기까지 시간복잡도와 BIG-O에 대한 내용을 정리해봤다.
수학을 잘 못해서.. 조금 어렵긴했지만 개념정도는 확실히 정리된 것 같아 뿌듯하다.
다음으로는 자료구조는 무엇이고 자료구조에서의 시간복잡도를 살펴볼 예정이다.

---

## Reference

[
CHAN-GPT - [자료구조] 알고리즘 성능평가를 위한 시간 복잡도 완벽히 이해하기! - (2)](https://chanos.tistory.com/entry/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EC%84%B1%EB%8A%A5%ED%8F%89%EA%B0%80%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%8B%9C%EA%B0%84-%EB%B3%B5%EC%9E%A1%EB%8F%84-%EC%99%84%EB%B2%BD%ED%9E%88-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-2#chap1)

[chulgil.lee - 알고리즘의 시간복잡도와 Big-O 쉽게 이해하기](https://blog.chulgil.me/algorithm/)