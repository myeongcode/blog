+++
author = "우명규"
title = "[Flutter] Scaffold Widget"
date = "2023-04-17"
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

> Flutter에서 `Scaffold`는 [_Material Design_](https://m3.material.io/)에서 사용되는 앱의 뼈대(Layout)을 제공하는 위젯입니다.

[_Scaffold class_](https://api.flutter.dev/flutter/material/Scaffold-class.html)

## 역할

`Scaffold`는 앱의 기본적인 레이아웃 구조를 정의하고, appbar, toolbar, drawer, tapbar 등과 같은 Material Design 구성요소를 구현합니다.

`Scaffold`는 일반적으로 `MaterialApp`위젯 내애서 사용되며, 앱의 뼈대를 제공하고, 많은 Material Design 구성요소를 간단하게 구현할 수 있기 때문에, Flutter앱을 개발할 때 매우 유용한 위젯 중 하나입니다.

`Scaffold` 위젯은 `body`속성을 통해 앱의 기본 컨텐츠를 정의하며, `appBar`속성을 통해 상단의 앱 바를 정의할 수 있습니다.

또한, `drawer`속성을 사용하여 측면 드로어를 추가하거나 `bottomNavigationBar`속성을 사용하여 하단의 탭바를 추가할 수도 있습니다.

![image](https://user-images.githubusercontent.com/67165016/232574889-3eaa6ab3-84d6-4903-bf60-53412d40ecf9.png)

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

---

### Appbar

> Application 최상단에 위치하고 있는 bar를 말합니다. 아래와 같이 `Scaffold`생성자에 AppBar를 전달하면 생성할 수 있습니다.

자세한 내용은 [_Appbar Class_](https://api.flutter.dev/flutter/material/AppBar-class.html)를 확인하세요

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'), //타이틀 제목
        centerTitle: true, //타이틀 가운데 정렬 (true/false)
      ),
    );
  }
}

```

![image](https://user-images.githubusercontent.com/67165016/232570649-24ed1411-b28f-4569-b602-e0ceff9771dc.png)

---

#### backgroundColor / foregroundColor

> 상단바의 배경색(backgroundColor) / 타이틀색(foregroundColor)를 지정할 때

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
        backgroundColor: Colors.green, //상단바 배경색
        foregroundColor: Colors.black, //상단바 타이틀색
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232571720-dd01397d-4df9-4d51-a472-95762082c64a.png)

---

#### elevation / shadowColor

> 상단바에 그림자효과를 줄 때

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
        elevation: 10, //상단바 Shadow 깊이
        shadowColor: Colors.red, //상단바 Shadow 색
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232572441-ad87dd6e-4e2a-45df-bafd-64ded898836d.png)

---

#### leading / actions

> 상단바에 앞(leading)/뒤(actions)에 아이콘과 같은 위젯들을 추가하고 버튼 아이콘으로 onPressed도 실행할 수 있음

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
        leading: const Icon(Icons.ac_unit), //상단바 타이틀 앞에 위젯추가
        actions: [
          //상단바 타이틀 뒤에 위젯추가
          IconButton(
            icon: const Icon(Icons.photo_album),
            tooltip: 'Hi!',
            onPressed: () => {},
          ),
          IconButton(
            icon: const Icon(Icons.pie_chart),
            tooltip: 'Wow',
            onPressed: () => {},
          )
        ],
        automaticallyImplyLeading: true, //뒤로가기 버튼 true(존재O)/false(존재X)
        centerTitle: true, //타이틀 가운데 정렬
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232573618-122d7705-0ffe-4d0b-9025-4f7fa6390dec.png)

---

### Body

> `Appbar`의 중간영역이며, `body`는 하나의 Widget만 가질 수 있으며 메인 화면에 보여질 내용을 주로 작성합니다.

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
      ),
      body: Center(
        child: Column(
          children: const [
            Text('1'),
            Text('2'),
            Text('3'),
            Text('4'),
            Text('5'),
            Text('6'),
          ],
        ),
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232578395-d3ae90f5-edde-4444-b2d4-978144e5d52d.png)

---

### Bottom Navigation Bar

> 앱 하단에 다른 뷰를 볼 수 있도록 메뉴바를 표시해주는 위젯입니다. 보통 페이지 별 바로가기 작업을 제공하기위해 만들어집니다.

자세한 내용은 [_BottonNavigationBar Class_](https://api.flutter.dev/flutter/material/BottomNavigationBar-class.html)를 확인하세요

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
      ),
      bottomNavigationBar: BottomNavigationBar(
        items: const <BottomNavigationBarItem>[
          BottomNavigationBarItem(
            icon: Icon(Icons.text_snippet),
            label: '나의 판매글',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.home),
            label: '홈',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.people),
            label: '마이페이지',
          ),
        ],
        selectedItemColor: Colors.lightGreen,
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232581045-996d5144-ffc3-42b8-8ade-0587256b4d3a.png)

---

### Floating Action Button

> 화면에 Fixed되는 원형 아이콘 버튼이며 일반적으로 화면 맨 하단 오른쪽에 위치하게 됩니다. Android 개발자들은 줄여서 `FAB`라고 부른다고 합니다. Icon뿐만아니라 Text로도 위젯을 사용할 수 있습니다.

자세한 내용은 [_FloationActionButton Class_](https://api.flutter.dev/flutter/material/FloatingActionButton-class.html)를 확인하세요

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('HomeScreen'),
      ),
      floatingActionButton: FloatingActionButton.extended(
        label: const Text('Approve'),
        icon: const Icon(Icons.thumb_up),
        backgroundColor: Colors.pink,
        onPressed: () => {print('hello')},
      ),
    );
  }
}
```

![image](https://user-images.githubusercontent.com/67165016/232583121-190f84a8-be5f-4cd6-b421-03a054e0e935.png)

---
