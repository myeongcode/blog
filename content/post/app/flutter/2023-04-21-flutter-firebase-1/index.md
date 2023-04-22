+++
author = "우명규"
title = "[Flutter] Flutter와 Firebase 연동하기 (Android)"
date = "2023-04-21"
description = "Firebase의 Auth서버를 Flutter와 연동해봅시다."
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

## Flutter 프로젝트 생성

먼저, Firebase와 연동할 Flutter프로젝트를 하나 생성해줍니다.

![image](https://user-images.githubusercontent.com/67165016/233696978-2ecb6e89-b234-4302-9624-063cb78e2660.png)

프로젝트 이름은 firebase_login으로 설정해줬음

그리고 프로젝트를 연 후 입력폼을 받을 스크린파일을 하나 만들어줍니다.

![image](https://user-images.githubusercontent.com/67165016/233697248-a6f19a72-feeb-4b8f-bb46-bdffe2b94ef5.png)

```dart
(lib > screens > login_screen.dart)

import 'package:flutter/material.dart';

class LoginScreen extends StatefulWidget {
  const LoginScreen({super.key});

  @override
  State<LoginScreen> createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  String userPassword = '';
  String userEmail = '';

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('LoginScreen'),
      ),
      body: GestureDetector(
        onTap: () {
          FocusScope.of(context).unfocus();
        },
        child: Center(
          child: Container(
            padding: const EdgeInsets.all(20),
            child: Column(
              children: [
                TextFormField(
                  keyboardType: TextInputType.emailAddress,
                  key: const ValueKey(1),
                  decoration: const InputDecoration(
                    hintText: 'email',
                    contentPadding: EdgeInsets.all(15),
                  ),
                  onSaved: (value) {
                    userEmail = value!;
                  },
                  onChanged: (value) {
                    userEmail = value;
                  },
                ),
                const SizedBox(
                  height: 20,
                ),
                TextFormField(
                  keyboardType: TextInputType.number,
                  key: const ValueKey(2),
                  decoration: const InputDecoration(
                    hintText: 'password',
                    contentPadding: EdgeInsets.all(15),
                  ),
                  onSaved: (value) {
                    userPassword = value!;
                  },
                  onChanged: (value) {
                    userPassword = value;
                  },
                ),
                const SizedBox(
                  height: 20,
                ),
                Container(
                  padding: const EdgeInsets.all(15),
                  height: 90,
                  width: 90,
                  decoration: BoxDecoration(
                    color: Colors.white,
                    borderRadius: BorderRadius.circular(20),
                  ),
                  child: GestureDetector(
                    onTap: () {
                      print(userEmail);
                      print(userPassword);
                    },
                    child: Container(
                      decoration: BoxDecoration(
                        borderRadius: BorderRadius.circular(50),
                        gradient: const LinearGradient(
                          colors: [
                            Colors.orange,
                            Colors.red,
                          ],
                          begin: Alignment.topLeft,
                          end: Alignment.bottomRight,
                        ),
                      ),
                      child: const Icon(
                        Icons.arrow_forward,
                        color: Colors.white,
                        size: 28,
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}
```

간단하게 입력폼으로 email과 password를 받아서 아래 버튼을 누르면 입력폼에 입력한 email과 password가 출력되게끔 만들었습니다.

![image](https://user-images.githubusercontent.com/67165016/233697699-3df3637a-7630-4b29-8a2d-e6c33ff26e24.png)

![image](https://user-images.githubusercontent.com/67165016/233698419-4c2acce9-81bf-4571-9b90-74d044327ed2.png)

잘 나오쥬? ㅎㅎ

---

## Firebase 연동

> [Firebase페이지](https://firebase.google.com/?hl=ko)에 접속해서 로그인을 해줍니다.

---

### Firebase 프로젝트 생성

로그인을 하고나면 `시작하기`로 클릭하여 프로젝트 생성창으로 들어옵니다.

![image](https://user-images.githubusercontent.com/67165016/233698747-9ded8b17-93b7-4593-abf2-682c2eeb5a77.png)

위에서 **프로젝트 추가**를 누릅니다.

![image](https://user-images.githubusercontent.com/67165016/233699205-eda992cb-dd21-4701-b7eb-c993c94416be.png)

프로젝트 이름은 가볍게 `login`으로 만들어주겠습니다.

![image](https://user-images.githubusercontent.com/67165016/233699490-476ab08f-d6b6-4247-b840-16305956055f.png)

애널리틱스 사용 설정을 냅두고 다음으로 넘어갑니다.

![image](https://user-images.githubusercontent.com/67165016/233699756-cd80603a-678a-4038-b721-9d26dec32dc8.png)

애널리틱스 위치를 `대한민국`으로 설정하고 프로젝트를 만듭니다.

프로젝트가 다 만들어지고 `계속`버튼을 누르면 다음화면이 표시됩니다.

![image](https://user-images.githubusercontent.com/67165016/233700205-fa480cfa-9d17-4113-a0f3-0b2940c322e1.png)

---

### Android 앱 등록

우리는 Android 기기를 연동할 것이므로 Android 아이콘표시를 누릅니다.

![image](https://user-images.githubusercontent.com/67165016/233700423-a4460d43-7089-4d79-8eef-6a18d2b17681.png)

![image](https://user-images.githubusercontent.com/67165016/233700780-4f74b3d0-01bf-45dd-b2d4-96ebc768d614.png)

그러면 위와같이 `Android 앱에 Firebase 추가`창이 나타납니다.

여기서 `Android 패키지 이름`은 우리가 만든 Flutter 프로젝트 내의 `android/app/build.gradle`파일에서 확인하실 수 있습니다.

![image](https://user-images.githubusercontent.com/67165016/233701010-829137dd-2d88-4351-857d-f22b2b09f448.png)

```gradle
(android > app > build.gradle)

  ...
  defaultConfig {
    ...
    applicationId "com.example.firebase_login" //이것이 android 패키지 이름
    ...
  }
  ...
```

`com.example.firebase_login`을 복사해서 android 추가하는 페이지에 붙여넣습니다.

![image](https://user-images.githubusercontent.com/67165016/233701737-959fc291-2b14-43ab-bd90-7fb8595a1458.png)

앱 닉네임은 정해도 좋지만, 우리는 그냥 기본값으로 쓰고 다음으로 넘어가보도록 하겠습니다.

![image](https://user-images.githubusercontent.com/67165016/233702029-7ecd923f-d3a3-4017-bd94-a36f28e92241.png)

![image](https://user-images.githubusercontent.com/67165016/233702419-ad6269ed-2831-4631-922f-00da69abd3e6.png)

위처럼 나온 설명대로 `google-services.json` 파일을 `android > app` 폴더 내에 넣어놓고 다음을 눌러줍시다.

![image](https://user-images.githubusercontent.com/67165016/233702812-0f3cbeb8-5b31-4737-b25c-8476f3731443.png)

1. `android > build.gradle` 파일에서 위와 같은 코드를 추가해줍니다.

```gradle
buildscript {
    ...
    repositories {
        google()
        mavenCentral()
    }

    dependencies {
        classpath 'com.google.gms:google-services:4.3.15'
        ...
    }
}

allprojects {
    repositories {
        google()
        mavenCentral()
    }
}
```

---

![image](https://user-images.githubusercontent.com/67165016/233703763-ad043da3-a7b7-4d07-ad14-695de4112f5b.png)

2. `android > app > build.gradle` 파일에서 위와 같은 코드를 추가해줍니다.

> 프로젝트에서 plugin쪽은 아마 `apply plugin: ~~`이런 식으로 되어있을 것임 맞춰서 넣어주면 됩니다.

```gradle
(android > app > build.gradle)

...
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services'
...

...

dependencies {
    implementation platform('com.google.firebase:firebase-bom:31.5.0')
    implementation 'com.google.firebase:firebase-analytics'
    ...
}
```

모두 코드를 추가해주었다면 다음 버튼을 눌러줍니다.

![image](https://user-images.githubusercontent.com/67165016/233704736-1f4ad4fa-8b88-482e-aa09-a7bdd2604903.png)

![image](https://user-images.githubusercontent.com/67165016/233704883-46113003-0b35-4df7-a992-dfb57ac4d354.png)

콘솔로 이동하면 다음과 같이 안드로이드 앱이 추가된 것을 확인할 수 있습니다.

### Flutter Package 설치

> Flutter에서 Firebase를 사용하기 위해서는 3가지 Package를 다운받아야 합니다.

#### **cloud_firestore**

클라우드 호스팅되는 noSQL 데이터베이스인 Cloud Firestore용 Flutter 플러그인은 Android 및 iOS에서 라이브 동기화 및 오프라인 지원을 제공

#### **firebase_core**

여러 Firebase 앱에 연결할 수 있는 Firebase Core용 Flutter 플러그인

#### **firebase_auth**

Firebase Auth용 Flutter 플러그인은 암호, 전화 번호 및 Google, Facebook 및 Twitter와 같은 ID 공급자를 사용하여 Android 및 iOS 인증을 가능하게 함

---

```yaml
(pubspec.yaml)

dependencies:
  flutter:
    sdk: flutter
  cloud_firestore: ^4.5.2
  firebase_core: ^2.10.0
  firebase_auth: ^4.4.2
```

---

### Firebase 초기화

패키지를 모두 다운받고 Flutter프로젝트로 돌아옵니다.

우리는 `firebase_core`라는 패키지를 설치하였는데, 플러터에서 firebase를 사용하기에 앞서 항상 초기화해주는 메서드인 `Firebase.initalizeApp()` 메서드를 호출해야합니다.

그렇지 않으면 다음과 같은 에러가 발생하게 됩니다.

![image](https://user-images.githubusercontent.com/67165016/233765024-40029ae1-e318-4333-9fab-1e71b6aabdb7.png)

이 코드는 `main.dart`에 넣어주도록 하겠습니다.

```dart
(lib > main.dart)

import 'package:firebase_login/screens/login_screen.dart';
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';

void main() {
  WidgetsFlutterBinding.ensureInitialized(); //Flutter 코어 엔진 초기화
  Firebase.initializeApp();
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const LoginScreen(),
    );
  }
}

```

`Firebase.initializeApp()` 메서드는 비동기 방식으로 작동하는 메서드입니다. 그래서 이 메서드는 플러터와 통신을 하고싶어하지만 플러터 최상위 메서드인 `runApp()` 메서드가 호출되기 전에는 Flutter 엔진이 초기화 되지 않아서 접근이 불가합니다.

메인메소드 내부에서 Flutter 엔진과 관련된 비동기 메서드를 사용하려면 먼저 Flutter 코어 엔진을 초기화시켜줘야 하는데, 이 역할을 하는 메서드가 `WidgetsFlutterBinding.ensureInitialized()` 입니다.

> 즉, Flutter에서 Firebase를 사용하려면 main메서드 내부에서 비동기 방식으로 `WidgetsFlutterBinding.ensureInitialized()` 을 호출하고 난 후 `Firebase.initalizeApp()` 을 호출해야합니다.

그리고 또, 비동기 방식으로 바꿔줘야하므로 다음과 같이 수정하면 됩니다.

```dart
(lib > main.dart)

import 'package:firebase_login/screens/login_screen.dart';
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const LoginScreen(),
    );
  }
}
```

---

### Firebase instance 생성

#### 사용자 SignUp 기능 구현

본격적으로 사용자 등록기능을 구현해보겠습니다.

우리가 만들었던 login_screen.dart에서 firebase_auth 패키지를 import하고 instance를 생성해주겠습니다.

한번 생성이 되면 변하지 않을 것이기 때문에 final타입으로 지정해주겠습니다. 그리고 외부에서 접근할 수 없도록 프라이빗(\_)으로 만들어주겠습니다.

```dart
(lib > screens > login_screen.dart)

import 'package:flutter/material.dart';
import 'package:firebase_auth/firebase_auth.dart';

class LoginScreen extends StatefulWidget {
  const LoginScreen({super.key});

  @override
  State<LoginScreen> createState() => _LoginScreenState();
}

class _LoginScreenState extends State<LoginScreen> {
  final _authentication = FirebaseAuth.instance;
  String userPassword = '';
  String userEmail = '';
  ...
```

우리는 사용자의 등록과 인증기능에 사용할 `_authentication`이라는 instance를 생성했습니다!

이 인스턴스로 우리는 이메일과 패스워드를 사용한 사용자 등록 메서드`.createUserWithEmailAndPassword()`이나 로그인을 할 수 있도록 만들어주는 메서드`.signInWithEmailAndPassword()`를 사용할 수 있습니다!

먼저 로그인기능을 만들기 전에 사용자를 등록하는 메서드를 만들어보겠습니다.

우리는 `userEmail`과 `userPassword`로 사용자의 이메일과 패스워드를 받아올 수 있었습니다.

그렇기때문에 다음과 같이 버튼을 눌렀을 때 해당 값이 인자로 넘어가게끔 만들어주면 됩니다.

```dart
(lib > screens > login_screen.dart)

...
  child: GestureDetector(
    onTap: () {
      _authentication.createUserWithEmailAndPassword(
        email: userEmail,
        password: userPassword,
      );
    },
...
```

예외처리를 생각한다면 다음과 같이 만들면 되겠죠?

정상적으로 사용자 등록이 되고나면 `ChatScreen()` 으로 넘어가게끔 만들어줍시다.

```dart
(lib > screens > login_screen.dart)

...
  child: GestureDetector(
    onTap: () async {
      try {
        final newUser = await _authentication
            .createUserWithEmailAndPassword(
          email: userEmail,
          password: userPassword,
        );

        if (newUser.user != null) {
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) {
                return const ChatScreen();
              },
            ),
          );
        }
      } catch (e) {
        print(e);
      }
    },
...
```

이 `ChatScreen()`에서 해당 사용자의 정보를 사용하려면 다음과 같이 instance를 생성해줘야합니다.

```dart
(lib > screens > chat_screen.dart)

import 'package:firebase_auth/firebase_auth.dart';
import 'package:flutter/material.dart';

class ChatScreen extends StatefulWidget {
  const ChatScreen({super.key});

  @override
  State<ChatScreen> createState() => _ChatScreenState();
}

class _ChatScreenState extends State<ChatScreen> {
  final _authentication = FirebaseAuth.instance;
  User? loggedUser;

  @override
  void initState() {
    super.initState();
    getCurrentUser();
  }

  void getCurrentUser() {
    try {
      final currentUser = _authentication.currentUser;
      if (currentUser != null) {
        loggedUser = currentUser;
        print(loggedUser);
      }
    } catch (e) {
      print(e);
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('ChatScreen'),
      ),
      body: const Center(
        child: Text("ChatScreen"),
      ),
    );
  }
}
```

이것도 마찬가지로 간단하게 예외처리를 하고 현재 로그인한 유저를 페이지가 로드되기 전에 데이터를 가져오게끔 만들기 위해 `initalState()`에 해당 함수를 불러오도록 하겠습니다

```dart
(lib > screens > chat_screen.dart)

import 'package:firebase_auth/firebase_auth.dart';
import 'package:flutter/material.dart';

class ChatScreen extends StatefulWidget {
  const ChatScreen({super.key});

  @override
  State<ChatScreen> createState() => _ChatScreenState();
}

class _ChatScreenState extends State<ChatScreen> {
  final _authentication = FirebaseAuth.instance;
  User? loggedUser;

  @override
  void initState() {
    super.initState();
    getCurrentUser();
  }

  void getCurrentUser() {
    try {
      final currentUser = _authentication.currentUser;
      if (currentUser != null) {
        loggedUser = currentUser;
      }
    } catch (e) {
      print(e);
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('ChatScreen'),
      ),
      body: Center(
        child: Text(
          loggedUser.toString(),
        ),
      ),
    );
  }
}
```

그러면 이제 등록을 위한 기능은 모두 마쳤습니다!

AVD를 다시 시작해봅시다!

---

#### 사용자 SignIn 기능 구현

로그인 기능을 하려면 다음과 같이 만들면 됩니다.

```dart
(lib > screens > login_screen.dart)

...
  child: GestureDetector(
    onTap: () async {
      try {
        final newUser =
          await _authentication.signInWithEmailAndPassword(
            email: userEmail,
            password: userPassword,
          );

        if (newUser.user != null) {
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) {
                return const ChatScreen();
              },
            ),
          );
        }
      } catch (e) {
        print(e);
      }
    },
...
```

---

#### Sdk version 에러

**minSdkVersion 16 cannot be smaller than version 19 declared in library**

간혹 이런 에러가 뜨게되는데 이건 아래 글에서 해결하시면 되겠습니다.

> https://myeongcode.github.io/p/flutter-sdk-version-%EC%98%A4%EB%A5%98/

---

### 계정 서버 생성

우리는 유저인증에 관련된 서버를 필요로하기때문에

![image](https://user-images.githubusercontent.com/67165016/233705233-ee7ee290-9877-41a2-9e27-56997fcfd87d.png)

왼쪽 탭에서 `빌드 > Authentication`으로 이동해줍니다.

![image](https://user-images.githubusercontent.com/67165016/233766774-1b174f57-3080-42d9-81a8-53260b3298e9.png)

시작하기를 눌러줍니다.

![image](https://user-images.githubusercontent.com/67165016/233766813-d2de1fc8-cc79-4a16-b470-6b3e489dbdf0.png)

다양한 기능이 있는데 우리는 `이메일/비밀번호` 로 기능을 만들어주겠습니다.

![image](https://user-images.githubusercontent.com/67165016/233766844-d51ce71a-1b96-470e-b889-97487eb187ec.png)

여기서 `이메일/비밀번호`의 사용설정을 체크해주고 저장을 누릅니다.

![image](https://user-images.githubusercontent.com/67165016/233766911-8f33e291-a316-440b-909a-985c9aed06f9.png)

사용설정을 마쳤습니다!!

그리고 `User`탭으로 한번 가보면 아직 사용자로 등록하지 않았으니 아무것도 뜨지 않을 겁니다.

![image](https://user-images.githubusercontent.com/67165016/233766956-bfdc5c36-95a5-452b-848c-797a00d07f09.png)

![image](https://user-images.githubusercontent.com/67165016/233768196-fb542b83-508b-4261-acb6-210d35015874.png)

한번 눌러볼까요?

![image](https://user-images.githubusercontent.com/67165016/233768267-5350ac3f-50bb-4c29-81f2-d3df674ab44a.png)

> ^오^ 성공이네요

## 참고자료

https://www.youtube.com/watch?v=se6wKk-w8lI&list=PLQt_pzi-LLfoOpp3b-pnnLXgYpiFEftLB&index=26
