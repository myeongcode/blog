+++
author = "우명규"
title = "[Flutter] 이미지 렌더링 오류 - 1"
date = "2023-04-21"
description = "HTTP request failed, statusCode: 403"
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

Image.network로 주소에 있는 이미지를 불러오려고 했지만 다음과 같이 화면이 깨지고 이미지가 출력되지 않음

```dart
(main.dart)

...
  return Column(
    children: [
      Image.network(webtoon.thumb),
      Text(webtoon.title),
    ],
  );
...
```

![image](https://user-images.githubusercontent.com/67165016/233627724-c3368c69-08a1-46c1-9dae-a5e7391ffa63.png)

## 에러 사진

![image](https://user-images.githubusercontent.com/67165016/233627889-68450ebd-672d-4a29-85b1-0bf74cc36aba.png)

---

## 원인

> 따로 User-Agent 값을 추가하지 않으면 기본값으로 `Dart/\<version> (dart:io)`가 들어갑니다.

참고 : [userAgent property](https://api.flutter.dev/flutter/dart-io/HttpClient/userAgent.html)

> 그래서 이 값을 지우고 브라우저에서 사용하는 값으로 바꿔줍니다.

---

## 해결방법

방법 1. **headers에 useragent 추가**

```dart
...
child: Image.network(
  webtoon.thumb,
  headers: const {"User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36",},
),
...
```

방법 2. **main.dart에서 class 추가**

```dart
class MyHttpOverrides extends HttpOverrides {
  @override
  HttpClient createHttpClient(SecurityContext? context) {
    return super.createHttpClient(context)
      ..userAgent = 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36';
  }
}

void main() {
  HttpOverrides.global = MyHttpOverrides();

  runApp(const App());
}

class App extends StatelessWidget {
  const App({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomeScreen(),
    );
  }
}
```

## 참고자료

https://gist.github.com/preinpost/941efd33dff90d9f8c7a208da40c18a9
