+++
author = "우명규"
title = "[Flutter] sdk version 오류"
date = "2023-04-21"
description = "minSdkVersion 16 cannot be smaller than version 19 declared in library"
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

cloud_firestore 패키지를 설치하고 AVD를 빌드 했을 때 발생한 오류

## 에러 사진

![image](https://user-images.githubusercontent.com/67165016/233767617-c549298f-64e5-439a-bd02-3b33199fc04f.png)

---

## 원인

> flutter에서 빌드 시, 특정 라이브러리가 minsdk버전을 충족하지 못하면 아래와 같은 에러가 발생하게 됩니다.

---

## 해결방법

`android > app > build.gradle`을 보면 다음과 같이 되어있다

![image](https://user-images.githubusercontent.com/67165016/233767879-d5f4f3f6-c2d3-47f8-b080-6300a30d3a12.png)

```gradle
    defaultConfig {
        applicationId "com.example.firebase_login"
        minSdkVersion flutter.minSdkVersion
        targetSdkVersion flutter.targetSdkVersion
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
    }
```

여기에서 minSdkVersion을 21로 변경해준다.

```gradle
    defaultConfig {
        applicationId "com.example.firebase_login"
        minSdkVersion 21
        targetSdkVersion flutter.targetSdkVersion
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
    }
```

## 참고자료

https://stackoverflow.com/questions/71495205/uses-sdkminsdkversion-16-cannot-be-smaller-than-version-19-declared-in-library
