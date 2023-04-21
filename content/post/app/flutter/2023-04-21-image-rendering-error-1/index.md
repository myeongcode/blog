+++
author = "우명규"
title = "[Flutter] 이미지 렌더링 오류 - 2"
date = "2023-04-21"
description = "Unable to load asset: ~"
tags = [
    "dart",
    "flutter",
]
categories = [
    "App",
]
image = "flutter-logo.png"
+++

<!--more-->

## 에러 내용

Image.asset을 이용해서 파일 경로로 이미지를 불러왔을 때 발생한 오류

```dart
(main.dart)

...
Image.asset(
  'images/google-logo.png',
  width: 70,
  fit: BoxFit.fill,
),
...
```

## 에러 사진

![image](https://user-images.githubusercontent.com/67165016/233625245-fbed94c7-191f-40ab-b2a5-0d2775fa8f65.png)

---

## 원인

> **pubspec.yaml에 assets를 추가해주지 않아 발생**하게 된 것

---

## 해결방법

pubspec.yaml 파일에 flutter > assets > images/ 라고 추가해줘야 이미지를 불러올 수 있게 됩니다.

즉, 사용할 assets의 경로를 설정해줘야합니다.

![image](https://user-images.githubusercontent.com/67165016/233625733-97f43d99-9fc4-44fc-92e1-f3d0622fedc2.png)

## 참고자료

https://security-nanglam.tistory.com/479
