+++
author = "우명규"
title = "[Join IT] Google I/O Extended 후기"
date = "2023-08-19"
description = "GDG Pangyo에서 진행하는 Google I/O 행사에 다녀왔습니다!"
tags = [
    "joinIt",
]
categories = [
    "Daily",
]
image = 'GDG-background.png'
+++

<style>
    .dis-row {
        display: flex;
        flex-direction: row;
    }

    .dis-col { 
        display: flex;
        flex-direction: column;
    }

    .jus-center {
        justify-content: center;
    }

    .jus-start {
        justify-content: flex-start;
        overflow-x: scroll;
    }

</style>

<!--more-->

## Google I/O Extended

[Google I/O Extended Pangyo Event](https://festa.io/events/3833)

### What's I/O Extended

> [I/O Extended](https://gdg.community.dev/ioextended/)는 GDG(Google Developers Group) 커뮤니티에 의해 전세계적으로 매년 개최되는 개발자 행사 중 하나이며, 보통 I/O Extended에서는 `구글 기술과 관련된 세션, 코드랩, 스터디잼`의 형태로 구성되며 진행됩니다.

### Order to Event

<div class="dis-row jus-center">
    <img width="300px" src="https://github.com/myeongcode/blog/assets/67165016/cb304bd2-f6b4-44a9-8453-5fd15a564cee" >
</div>

---

## Welcome to Google I/O Extended!!

판교 테크원 건물 4F에서 진행을 하였고, NAVER의 여러 자회사들도 해당 건물에 위치해있어 기념으로 사진을 찍었다.

<div class="dis-row jus-center">
    <img width="400px" src="https://github.com/myeongcode/blog/assets/67165016/f5ec9686-83ad-40dd-88ca-ce81f7aec83a" >
</div>

그리고는 Google I/O Extended 행사장에 도착하여, GDG의 스티커와 티셔츠도 함께 제공받았다!

<div class="dis-row jus-start">
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/ed1bc625-7cc2-4003-8d4b-83188aa9d857" >
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/d9faa9b4-c0b9-483a-8d7f-db8fbc9ab7c3" >
</div>

---

### `Google I/O Connect` by GDG Pangyo 조희주님

> **Point 👉🏻** 기술적인 세션보다는 GDG 활동을 하면서 커넥트한 경험을 알려주셨다.

GDSC 활동을 하면서 커뮤니티라는 느낌을 받은 적이 없는데, GDG는 커뮤니티적인 활동들을 많이 하시는 것 같다. 국내뿐만 아니라 해외의 GDG와도 커넥트를 하기위해 마이애미와 동아시아, 뉴질랜드사람들과도 만나셨다고 한다.

또한, GDG분들과도 18년도부터 꾸준히 커뮤니케이션해왔다고 한다. 확실히 GDSC보다 조금 더 활발한 커뮤니티 그룹인 것 같아 추후에 들어가보고 싶은 마음이 생겼다.

---

### Keras core : changes and challenges by 래블업 신정규님

> **Point 👉🏻** AI에서 사용되는 근본인 Keras가 Keras core가 되어 나타난 이유와 역사

<div class="dis-row jus-center">
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/e66e7040-abda-479b-9bbb-50e2771f77ba" >
</div>

AI에 대해 전무한 나에게는 너무나 어려운 내용이였다..
그래도 Keras Core라는 것이 Tensor flow와 JAX 등을 함께 사용할 수 있는 커스텀 컴포넌트 멀티 프레임워크라는 점은 배웠다.

금주부터 AI에 대한 교육을 받는데 어느정도 도움이 되었으면 좋겠다.

---

### Android Update 2023 by 레몬트리 권태환님

> **Point 👉🏻** Android 14버전의 변경이슈와 Android가 재미없는 이유

<div class="dis-row jus-center">
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/885ac850-728b-42ab-9504-b1dee4486c5c" >
</div>

곧 정식출시될 안드로이드 14는 정책에 관련된 변경점과 보안 세션에 관련된 내용만 주로 업데이트가 되었다고 하셨다. 예전에는 Android가 프리해서 개발자들이 좋아했다는데 점점 iOS랑 닮아가고 제한되는 부분들이 많아지면서 재미가 없다고 10년차 안드로이드 개발자분께서 말씀을 하셨...ㅠ ㅋㅋ

그리고, 새로운 기능들도 생겼다고 하셨는데 왜 생겼는지 모르겠다고 하셨닼ㅋㅋ

대신 Compose에 대한 내용을 많이 설명해주셨다. Compose로 iOS, Android, Web, Android TV까지 사용할 수도 있다고(완벽히 호환되지는 X)하셨다. 그래서, 꾸준히 안드로이드를 하면 모든 플랫폼을 개발할 수 있는 기대를 가지고 계신다고 말씀해주셨다.

---

### React18, 제로 번들을 향한 새로운 시작 by 당근마켓 이동근님

> **Point 👉🏻** React18의 게임체인저 RSC의 구조와 장점과 단점

<div class="dis-row jus-center">
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/16a4721d-4d02-43a6-9406-3e3951dac198" >
</div>

사실, 프론트엔드에 관심이 많았던 나는 이 세션이 가장 듣고싶었다. 자바스크립트가 많이 발전해오면서 SSR과 CSR, Universal SSR의 장점과 단점 그리고, Server Component인 RSC의 등장까지 말씀해주셨다.

Server Component는 간단히 말하면 **일부 컴포넌트는 Client에서 렌더링되고, 일부는 서버에서 컴포넌트가 렌더링돼서 Client**로 보내주는 방식이다.

<div class="dis-row jus-center">
    <img width="600px" src="https://github.com/myeongcode/blog/assets/67165016/cb8a164b-474a-459d-8d6e-ce3f41a44863" >
</div>

#### RSC와 SSR의 차이점

👉🏻 일부가 서버에서 렌더링된다면 SSR이랑 같은거 아냐?
라고 생각할 수도 있지만, 서버라는 이름만 같지 전혀 다른 개념을 보여주고 있다.

SSR의 경우는 html을 변환하고 변환된 것을 js로 다운받는 형태고 그 후 Hydration 작업과정을 거쳐 HTML 코드와 JS 코드를 서로 매칭시켜 동적인 웹사이트를 브라우저에 랜더링하는 형태지만, Server Component는 서버에서 동작하지만 실제로 바로 동작이 가능한 jsx 컴포넌트 단위로 내려줍니다.

그렇기에 Hydration 작업이 필요없이도 바로바로 interaction이 가능하다고 말씀하셨다.

#### SSR

<div class="dis-row jus-center">
    <img width="500px" src="https://github.com/myeongcode/blog/assets/67165016/7ae59cbc-6eaa-47a6-bec3-13f69d24f09c" >
</div>

#### RSC

<div class="dis-row jus-center">
    <img width="500px" src="https://github.com/myeongcode/blog/assets/67165016/479b6e61-12de-4c42-b796-4642d259c24d" >
    <!-- <img width="500px" src="https://github.com/myeongcode/blog/assets/67165016/f376e75a-3fda-4c16-9545-34d5e147206c" > -->
</div>

결국, 이러한 RSC는 더 나아가서 DB에 직접 접근하여 API요청 정보라든지 보안적인 부분에서 숨길 수 있게되고, 바로 인터렉션이 가능한 컴포넌트만 받아와서 사용할 수 있습니다.
즉, 렌더링에 필요한 번들이 필요없다는 Zero-bendle이 가능해진다는 의미겠죠.

근데 마냥 RSC가 좋다고 할 수 있을까요?
서버 컴포넌트는 리액트의 심장인 Hooks를 사용하지 못합니다. 그래서 상태관리 또한 RSC에서는 어려워지죠.

그리고, emotion이나 styled-component같은 css-in-js를 사용할 수 없습니다.

또, RSC에 대한 reference가 별로 없습니다.
이제 react 18에 탑재된 만큼 아직 안정성과 효율성적인 측면에서도 보장을 못하고, 블로그를 작성하면서 찾아봐도 참고할 수 있는 것들이 별로 없었습니다.

#### 요약

`RSC(React Server Component)`는 SSR과 다르게 서버에서 바로 인터렉션이 가능한 컴포넌트 형태로 구성될 수 있으며, 일부는 Server Component 또 나머지 일부는 Client Component로 구현할 수 있습니다.

**<p style="font-size: 20px;">장점</p>**

1. 제로 번들링이 가능
2. 번들이 없으니 페이지 이동간 상태공유 렌더링 성능이 빨라짐
3. 보안적인 측면에서 강화

**<p style="font-size: 20px;">단점</p>**

1. 리액트의 Hooks를 사용하지 못함
2. 상태관리가 어려워짐
3. css-in-js를 사용하지 못함

## 후기

👉🏻 옵셔널 드레스코드가 하와이안 룩으로 되어있었는데, 몇몇분이 하와이안 룩으로 입고 오신 것을 봤다.. 존경스럽다... 나도 슈퍼관종이였으면 입고갔을텐데 아쉽게도 슈퍼까진 아니였던걸로..🤭

GDG에서 진행하는 행사인만큼 기대를 했고, 이벤트 상 순서에서는 세션이 종료 후 네트워킹 시간이 따로 배정되어있어있던걸 봤는데 세션이 끝나고 바로 종료가돼서 뭐지..? 싶었다. 오신 다른 개발자분들과도 함께 네트워킹해보고 싶었는데 ㅠㅠ..

그래도 남아서 필요한 질의응답을 했고, 링크드인도 얻었다!

친구랑 함께 기념사진을 찍고 마무리했다!

<div class="dis-row jus-center">
    <img width="500px" src="https://github.com/myeongcode/blog/assets/67165016/fca713cf-55ec-4cb0-9a6c-bf4ed44b74bb" >
</div>

## 관련자료

1. [Tapas adhikary님의 React Server Components – How and Why You Should Use Them in Your Code](https://www.freecodecamp.org/news/how-to-use-react-server-components/)
