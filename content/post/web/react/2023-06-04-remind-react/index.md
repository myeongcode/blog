+++
author = "우명규"
title = "[React] React에 대한 정리"
date = "2023-06-04"
description = "잃었던 React의 감을 다시 한번 살려보자!"
tags = [
    "react",
]
categories = [
    "Web",
]
image = "react-logo.png"
+++

<!--more-->

## 서론 🌐

React에 대해서 정확히 설명할 수 없었던 나이기에 React를 사용했던 경험을 떠올려 다시한번 복습을 하고 정확한 React를 알기 위해 정리를 해보겠습니다.

## React란?

> React는 웹 프레임워크로 자바스크립트 라이브러리의 하나로서 특히 **SPA(Single Page Application)을 위한 사용자 인터페이스를 구축**하는데 사용됩니다.

즉, 현재 많이 활용되고 있는, 웹/앱의 View를 개발할 수 있는 인기 라이브러리죠

### SPA(Single Page Application)

> 단일 페이지 어플리케이션

즉, **어떠한 웹 사이트의 전체 페이지를 하나의 페이지에 담아 동적으로 화면을 변경해 표시하는 기술**

더 자세한 내용은 아래 링크에서 확인

[JONGMINFIRE.DEV님의 "SPA(Single Page Application)란?"](https://jongminfire.dev/spa-single-page-application-%EB%9E%80)

## React의 필요성

사실은 React를 사용하지 않아도, html과 css, javasciprt를 이용해서 웹 페이지를 만들 수 있지만, react를 이용하면 사용자와 상호작용할 수 있는 동적인 UI를 쉽게 만들 수 있습니다.

### SPA을 만들 때 좋습니다.

> 모바일 앱처럼 전체화면 새로고침 없이 부드럽게 만들고 싶을 때 사용합니다.

### 재사용이 편리합니다.

> html을 함수, array, object 이런 곳에 보관하고 재사용할 수 있어서 큰 프로젝트 일 수록 html 관리가 편리해집니다.
> 또, **ReactNative를 쓰면 같은 리액트 문법으로 모바일 앱개발도 가능**합니다.

## React 특징

### JSX

React에서는 템플릿에 일반 JavaScript를 사용하는 대신 JSX를 사용합니다. JSX는 **HTML 인용을 허용하고 이러한 HTML 태그 구문을 사용하여 하위 구성 요소를 렌더링**하는 간단한 JavaScript입니다.

### Data Flow(Flux)

React는 데이터의 흐름이 한 방향으로만 흐르는 단방향 데이터 흐름(Flux)을 가집니다.

Angular.js와 같은 양방향 데이터 바인딩은 규모가 커질수록 데이터의 흐름을 추적하기가 힘들고 복잡해지는 경향이 있어, 복잡한 앱에서도 데이터 흐름에서 일어나는 변화를 보다 예측가능할 수 있도록 단방향 흐름을 가지도록 했다고 합니다.

### Component 기반 구조

> Component는 독립적인 단위의 소프트웨어 모듈을 말합니다.
> 즉, 소프트웨어를 독립적인 하나의 부품으로 만드는 방법이라고 볼 수 있습니다.

React는 UI(View)를 여러 컴포넌트로 쪼개서 만듭니다.
한 페이지 내에서도 여러 각 부분을 독립된 컴포넌트로 만들고, 이 컴포넌트를 조립해 화면을 구성합니다.

컴포넌트 단위로 쪼개져있기 때문에, 전체 코드를 파악하기 상대적으로 쉽습니다. 이렇게 기능 단위, UI 단위로 캡슐화시켜 코드를 관리하기 때문에 재사용성이 높습니다.

```jsx
class App extends Component {
  render() {
    return (
      <Layout>
        <Header />
        <Navigation />
        <Content>
          <Sidebar></Sidebar>
          <Router />
        </Content>
        <Footer></Footer>
      </Layout>
    );
  }
}
```

### Virtual DOM (Document Object Model)

원래, DOM은 html, xml, css 등을 트리 구조로 인식하고, 데이터를 객체로 간주하고 관리합니다.

하지만, 페이지를 수정할 때 마다 DOM 트리를 계속 새로 그려줘야하고 수정할 데이터를 DOM에서 모두 찾아서 수정해야하기 때문에 성능과 비용적인 측면에서 손실이 큽니다.

그래서 React에서는 **DOM Tree 구조와 같은 구조체 Virtual DOM이라는 가상의 문서 객체 모델**을 만들어 이벤트가 발생할 때 마다 Vitrual DOM을 만들고 다시 그릴 때마다 실제 DOM과 비교하고 전/후 상태를 비교해, 변경이 필요한 최소한의 변경사항만 실제 DOM에 반영해, 앱의 효율성과 속도를 개선할 수 있습니다.

### Props & State

- Props

  **props는 부모 컴포넌트에서 자식 컴포넌트로 전달해주는 데이터**를 말합니다
  쉽게 읽기 전용 데이터라고 생각하면 될 것 같습니다. 자식 컴포넌트에서 전달받은 Props는 변경이 불가능하고 props를 전달해준 최상위 부모 컴포넌트만 props를 변경할 수 있습니다.

- State

  **State는 컴포넌트 내부에서 선언하며 내부에서 값을 변경**할 수 있습니다. state는 동적인 데이터를 다룰 때 사용하며, 사용자와의 상호작용을 통해 데이터를 동적으로 변경할 때 사용합니다. 다만, state를 바꿀 때에는 `[state, setState] = useState(value)`형식에서 `setState()`라는 함수로 변경해야합니다.

## React 장단점

### React의 장점

1. **빠른 업데이트와 렌더링 속도**

   위에서 말했듯, React는 빠른 업데이트를 위해 Virtual DOM이라는 것을 사용하여 어떤 DOM 상태의 변경이 일어나야한다면 Vitrual DOM에서는 변경해야 할 최소한의 부분을 검색(Compute Diff)하여 검색한 부분만을 업데이트하고 렌더링하기 때문에 렌더링 속도가 상대적으로 빨라진다.

2. **재사용성**

   리액트는 모든 페이지가 컴포넌트로 구성되어져있고 하나의 컴포넌트는 다른 여러 개의 컴포넌트로 구성되어 질 수 있습니다. 마치 레고 블록을 조립하듯 컴포넌트들을 조립해서 개발할 수 있다는 것입니다.

3. **활발할 지식공유 및 커뮤니티**

   구글링만 해도 잘 나온다.

4. **React Native**

   리액트 문법을 사용해서 모바일 환경도 개발할 수 있다는 장점이 있다.

### React의 단점

1. IE8 이하 버전은 지원하지 않는다.

2. View 이외의 기능은 직접구현하거나 라이브러리를 사용해서 구현해야하기에 javascript 배경지식이 필수 선생이다.

3. 데이터 모델링, 라우팅, Ajax 등 기능 지원이 안된다.

4. 앱의 규모가 커지면 속도가 느려진다.

5. 높은 상태관리 복잡도
