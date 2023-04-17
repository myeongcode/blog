+++
author = "우명규"
title = "[Flutter] Scaffold Widget"
date = "2023-04-18"
description = "Scaffold의 개념과 역할 그리고 사용법"
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

## Scaffold란?

> Flutter에서 `Scaffold`는 (Material Design)[https://m3.material.io/]에서 사용되는 앱의 뼈대(Layout)을 제공하는 위젯입니다.

## 역할

`Scaffold`는 앱의 기본적인 레이아웃 구조를 정의하고, appbar, toolbar, drawer, tapbar 등과 같은 Material Design 구성요소를 구현합니다.

`Scaffold`는 일반적으로 `MaterialApp`위젯 내애서 사용되며, 앱의 뼈대를 제공하고, 많은 Material Design 구성요소를 간단하게 구현할 수 있기 때문에, Flutter앱을 개발할 때 매우 유용한 위젯 중 하나입니다.

`Scaffold` 위젯은 `body`속성을 통해 앱의 기본 컨텐츠를 정의하며, `appBar`속성을 통해 상단의 앱 바를 정의할 수 있습니다.

또한, `drawer`속성을 사용하여 측면 드로어를 추가하거나 `bottomNavigationBar`속성을 사용하여 하단의 탭바를 추가할 수도 있습니다.

## parameter

> Scaffold의 parameter는 다양하지만, 우리는 가장 범용적으로 사용하는 기능에 대해 다룰 것입니다.

```dart
class Scaffold extends StatefulWidget {
  const Scaffold({
    super.key,
    this.appBar,
    this.body,
    this.floatingActionButton,
    this.floatingActionButtonLocation,
    this.floatingActionButtonAnimator,
    this.persistentFooterButtons,
    this.persistentFooterAlignment = AlignmentDirectional.centerEnd,
    this.drawer,
    this.onDrawerChanged,
    this.endDrawer,
    this.onEndDrawerChanged,
    this.bottomNavigationBar,
    this.bottomSheet,
    this.backgroundColor,
    this.resizeToAvoidBottomInset,
    this.primary = true,
    this.drawerDragStartBehavior = DragStartBehavior.start,
    this.extendBody = false,
    this.extendBodyBehindAppBar = false,
    this.drawerScrimColor,
    this.drawerEdgeDragWidth,
    this.drawerEnableOpenDragGesture = true,
    this.endDrawerEnableOpenDragGesture = true,
    this.restorationId,
  })
```

### Appbar

---

Application 최상단에 위치하고 있는 bar를 말합니다.
아래와 같이 `Scaffold`생성자에 AppBar를 전달하면 생성할 수 있습니다.
