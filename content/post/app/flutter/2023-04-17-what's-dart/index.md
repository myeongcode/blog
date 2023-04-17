+++
author = "우명규"
title = "[Dart] Flutter에서 사용하는 Dart언어란?"
date = "2023-04-17"
description = "Dart언어가 무엇일까?"
tags = [
    "dart",
    "flutter",
]
categories = [
    "App",
]
image = "dart-logo.png"
+++

<!--more-->

## Dart란?

Dart는 구글이 디자인한 **멀티 플랫폼 프로그래밍언어**입니다.

자바스크립트를 대체할 수 있는 크로스 플랫폼 프로그래밍 언어를 목표로 설계했다고 합니다.

Dart는 Flutter에서 사용되는 언어이며 모든 플랫폼에서 빠른 앱을 위한 클라이언트 최적화 언어입니다.

1. **UI 최적화용** : 사용자 인터페이스 생성 요구에 특화된 프로그래밍 언어로 개발

2. **생산적인 개발** : 핫 리로드를 사용하여 실행 중인 앱에서 즉시 결과 확인

3. **모든 플랫폼에서 빠름** : 모바일, 데스크톱 및 백엔드용 ARM 및 x64 머신 코드로 컴파일합니다. 또는 웹용 JavaScript로 컴파일

[Dart 공식 사이트]

[dart 공식 사이트]: https://dart.dev/

사이트에 본 설명에 의하면 Dart는 두 개의 컴파일러를 가지고 있다.

![](https://dart.dev/assets/img/Dart-platforms.svg)

- **Dart Web** : Dart로 쓴 코드를 javascript로 변환해주는 컴파일러
- **Dart Native** : Dart로 쓴 코드를 여러 CPU의 아키텍쳐에 맞게 변환해주는 컴파일러
  (ARM32, 모바일인 ARM64(IOS, Android), 데스크탑인 x86_64(Mac, Linux, Windows) 등등에 맞게 변환해준다는 의미)

## JIT, AOT

Dart는 또 어떻게 컴파일 되는지에 대해 JIT, AOT로 볼 수 있다.

- **JIT(Just-In-Time)** : **개발 중**에는 수정된 코드가 결과로 바로 나타날 수 있게끔 만드는 컴파일러로 Dart VM(Virtual Machine)을 사용하여 Just-In-Time 컴파일러를 제공합니다.
- **AOT(Ahead-of-time)** : **배포를 할 때**에는 더이상 Dart VM(Virtual Machine)을 사용하지 않고 Ahead-Of-Time 컴파일러를 제공하여 각 아키텍쳐에 맞는 기계어로 컴파일이 되고 앱을 더 빠르게 실행시킬 수 있게 만듭니다.

이러한 특징을 갖는 것은 모바일 개발에 있어서 아주 중요하고 멋진 특징입니다.
개발 중에 바로바로 피드백을 확인할 수 있고, 앱을 배포할 때에는 휴대폰, 노트북, 웹사이트에서 기계어를 실행하여 편하게 배포를 할 수 있습니다.

## null safety

> 다른 언어에서는 코드에서 null 값을 참조해버리면 오류가 발생하여 더 이상 동작을 할 수 없게 만들지만, Dart는 이러한 문제를 방지하기 위해 null safety라는 것을 도입했습니다.

## 결론

Flutter는 Dart라는 언어를 사용하는데 둘 다 구글에서 제작한 것이므로 Dart는 Flutter를 위한 언어라고 볼 수 있습니다. 그래서 Flutter에서의 Dart언어를 최적화하고싶다면 수정을 할 수 있다는 큰 장점이 있습니다.

이것이 중요한 이유는 React나 Vue는 언어에 대해 최적화를 하고싶다고 하여도 javascript를 수정할 수 없습니다. 다른 언어들도 마찬가지입니다. 그렇기때문에 이 점은 매우 강한 장점으로 보이며 그 속에 또 다른 단점이 존재할 수 있습니다.
하지만, RN에 비해 Flutter의 사용비율이 급격히 증가해지면서 커뮤니티가 활성화되고있고 더 많은 기능을 기대할 수 있을 것 같습니다.

Flutter에 관심이 많다면 한번 배워보는 것도 좋을 것 같습니다.
