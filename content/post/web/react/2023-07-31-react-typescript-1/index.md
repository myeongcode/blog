+++
author = "우명규"
title = "[React] React + Typescript 실무에서 사용하는 프로젝트 셋팅법!"
date = "2023-07-31"
description = "'현장에서 바로 써먹는 리액트 With 타입스크립트' 2장 - 실무에서 자주 사용되는 개발환경을 조성해보자!"
tags = [
    "react",
]
categories = [
    "Web",
]
image = "react-logo.png"
+++

<!--more-->

## 들어가며

React 프로젝트를 처음 시작하게 될 때, 저처럼 프론트엔드 초보자인 분들은 npm install만 하고나서 어떻게 해야할지 모를 때가 있을 것 같습니다.

최근에도, 프로젝트를 처음으로 시작하는데 어떤 기술을 써야할지 프로젝트 셋팅은 어떻게 해야할지 자꾸 까먹게되서 그냥 이참에 프로젝트 초기 셋팅하는 법을 확실하게 알고, 또 추후에 React + Typescript로 프로젝트를 진행하게 될 때 좀 더 빠르게 초기 설정을 하기위해 이 포스트를 작성하려합니다.

사실, 프로젝트에서 기획에 맞는 어떤 기술을 사용할거냐부터 정하는게 우선이긴 하지만 우리는 React + Typescript로 정했다는 가정하에 진행을 하려합니다.

필요하면 어떤 서비스를 하게될 때 어떤 기술을 사용할지 파악하는 글도 추후에 올려볼려고합니다.

어쨋든, 서론이 길었는데 한줄로 요약하자면 **프로젝트 초기설정을 쉽고 빠르게 하기위함**이 이 글의 목표입니다.

## 프로젝트 초기 환경 셋팅

본인이 가지고 있는 환경은 맥OS이나 추후에 윈도우에서 충분히 쉽게 사용할 수 있도록 윈도우 환경, 맥 환경 둘 다 셋팅할 수 있는 방법을 적을 것입니다.

### 윈도우 개발 환경 설정

React 프로젝트를 사용하기 위해서는 반드시 노드 설치가 필요합니다

#### 초콜리티 설치

초콜리티(Chocolatey)는 윈도우에서 패키지를 설치하고 관리할 수 있는 윈도우용 패키지 관리자입니다
맥에서의 Homebrew와 같은 역할을 한다고 보시면 됩니다

긴말 말고, 바로 아래 링크를 통해 초콜리티 다운로드를 합니다.

> https://chocolatey.org/install

그럼 아래와 같은 페이지가 뜰 텐데, 여기서 Now run the following command에 있는 명령어를 복사하여

![](https://github.com/myeongcode/blog/assets/67165016/18596f13-4f94-48a2-8c27-bc5ad1ad0a0f)

명령 프롬프트(cmd)또는 파워셸(PowerShell)을 관리자 권한으로 실행한 후, 위에서 복사한 코드를 붙여넣기한다.

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

설치가 완료되면 다음 명령어를 실행시켜 초콜리티가 잘 설치됐는지 확인합니다

```shell
choco -version
```

문제없이 설치되었다면 버전이 뜨게 될 것입니다.

#### 노드 설치

초콜리티가 설치되었으면 이제 노드를 설치해보도록 하겠습니다.

리액트는 자바스크립트 라이브러리로, 프로젝트를 생성하고 개발에 필요한 외부 라이브러리를 사용할 때에 노드 패키지(Node Package)를 이용하게 됩니다.

따라서 리액트로 개발하기 위해서는 노드를 꼭 설치해야합니다.

윈도우의 명령 프롬프트를 관리자 권한으로 실행시킨 후 다음 명령어를 실행시켜 노드를 설치합니다.

```shell
choco install -y nodejs.install
```

설치가 완료되면 명령프롬프트를 다시 실행시킨 후 다음 명령어를 실행시키면 노드의 버전이 나오면서 노드가 잘 설치되었는지 확인할 수 있습니다

```shell
node --version
```

---

### 맥 개발 환경 설정

#### 홈브루 설치

홈브루(Homebrew)는 패키지를 설치하고 관리할 수 있는 맥용 패키지 관리자입니다.

우선 아래 링크를 통해서 맥에 홈브루를 설치합니다.

> https://brew.sh/index_ko (설치법은 해당 링크에 잘 설명되어있음)

#### 노드 설치

터미널을 열고 다음 명령어를 실행하여 노드를 설치합니다

```
brew install node
```

설치가 완료되면 명령어로 노드가 제대로 설치되었는지 확인한다

```
node -v
```

노드를 설치하면, 노드의 패키지를 관리하는 노드 패키지 매니저인 npm(Node Package Manager)도 같이 설치된다. 이것도 잘 설치되어있는지 확인한다.

```
npm -v
```

---

### 리액트 프로젝트 시작

리액트를 사용하여 프로젝트를 시작하는 방법은 다양합니다.

- 스크립트 태그 추가
- Webpack이나 Babel을 설정하여 개발
- CRA(create-react-app)
- Next.JS 프레임워크 설치

우리는 CRA방식으로 진행을 할 것이지만 다른 것들은 어떻게 다른지 간단하게 살펴보면 좋을 것이다.

#### 스크립트 태그 추가

리액트는 자바스크립트 라이브러리이므로 jQuery와 같은 보통의 자바스크립트의 사용방법과 동일하게 스크립트 태그를 추가하여 사용할 수 있습니다

```js
<body>
  ...
  <div id="app"></div>
  ...
  <script async src="https://unpkg.com/lodash"></script>
</body>
```

기존에 그냥 JS로만 작성되어있는 웹서비스인 경우에는 빠르게 리액트로 시작할 수 있는 방법이지만, 고려해야할 사항이 많다.

#### Webpack이나 Babel을 설정하여 개발

크로스 브라우징 문제와 최신 ECMAScript, Typescript등을 사용하여 리액트 프로젝트를 진행하기 위해서는 Webpack, Babel을 설정하여 개발을 할 수 있습니다.

> https://goo-gy.github.io/2021-12-31-webpack-react (goo-gy님의 Webpack을 이용한 React개발)

하지만, Webpack이나 Babel을 잘 알아야하기때문에 초보자들에게는 큰 어려움이 있습니다.

#### CRA(create-react-app)

Webpack이나 Babel을 설정하여 개발하는 방법에 대해 어려움을 인지한 페이스북이 create-react-app이라는 CLI(Command Line Interface) 툴을 만들어서 배포했습니다.

> https://create-react-app.dev/

보편적으로 제일 많이 사용하기도 하고, 이 툴을 사용하면 간단하게 리액트 프로젝트를 생성하고 개발할 수 있습니다

#### Next.JS 프레임워크

이건 React만을 사용하는게 아닌 더 많은 기능을 제공하는 프레임워크인 만큼 Next.js만이 가진 기능과 고유한 방법들이 있기때문에 React를 어느정도 알고난 후 SSR과 router을 사용하고싶다하면 그때 공부해도 괜찮을 것 같다.

---

### create-react-app

그러면 create-react-app으로 리액트를 개발하는 방법에 대해 알아보자

#### create-react-app 설치

다음 명령어를 실행하여 create-react-app을 설치합니다.

```shell
npm install -g create-react-app
```

다음 명령어를 사용하여 문제없이 설치되었는지 확인합니다

```shell
npx create-react-app --version
```

> **여기서 헷갈리면 안되는 점!** 👉🏻 `npm`은 패키지를 설치할 때 사용하는 명령어이고, `npx`는 npm을 통해 설치한 패키지를 실행할 때 사용하는 명령어

#### create-react-app으로 프로젝트 생성 및 실행

다음 명령어를 통해 React 프로젝트를 생성해봅시다.

```shell
npx create-react-app my-app
```

여기까지는 일반적인 React 프로젝트를 생성하는 방법이지만, 우리는 더 Typescript와 실무에서 사용되는 Emotion, prettier까지 설정을 해볼 것입니다.

---

### React 프로젝트를 Typescript로 설정

React프로젝트를 Typescript로 설정하는 방법에는 2가지 존재합니다

- 기존 React프로젝트에서 Typescript를 설정
- CRA로 프로젝트 생성과 동시에 Typescript를 설정

#### 기존 React프로젝트에서 Typescript를 설정

이미 생성되어있는 리액트 프로젝트에 타입스크립트를 적용하기 위해서는 타입스크립트 라이브러리와 리액트의 타입이 정의된 타입 정의 파일을 설치할 필요가 있습니다.

- **typescript** : 타입스크립트 라이브러리
- **@types/node** : 자바스크립트 런타임인 노드의 타입이 정의된 타입 정의 파일
- **@types/react** : 리액트의 타입이 정의된 타입 정의 파일
- **@types/react-dom** : react-dom의 타입이 정의된 타입 정의 파일

해당 프로젝트의 터미널에서 다음 명령어를 실행시킵니다.

```shell
npm install --save-dev typescript @types/node @types/react @types/react-dom
```

설치가 완료되었다면 해당 프로젝트의 루트 폴더에서 `tsconfig.json`파일을 생성하고 내용을 다음과 같이 수정합니다.

```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx"
  },
  "include": ["src"]
}
```

위와 같이 작성했다면 자바스크립트 파일들을 타입스크립트 파일로 변경합니다.

- ./src/App.js 👉🏻 ./src/App.tsx
- ./src/App.test.js 👉🏻 ./src/App.test.tsx
- ./src/index.js 👉🏻 ./src/index.tsx
- ./src/reportWebVitals.js 👉🏻 ./src/reportWebVitals.ts
- ./src/setupTest.js 👉🏻 ./src/setupTest/ts

다음으로는 기존의 자바스크립트 코드를 타입스크립트를 사용하여 변경해야합니다.
우선 svg 파일을 타입스크립트에서 불러올 수 있게 하기위해 `./src/custom.d.ts`파일을 생성하고 다음과 같이 수정합니다.

```js
declare module "*.svg" {
  export const ReactComponent: React.FunctionComponent<React.SVGProps<SVGSVGElement> & { title?: string }>;

  const src: string;
  export default src;
}
```

> 여기서 생성하는 d.ts 파일은 타입 정의 파일로 **타입스크립트가 인식하지 못하는 타입이지만, 타입스크립트 안에서 사용할 특정 타입들을 정의할 때 사용**합니다.

그리고 ./src/reportWebVitals.ts 파일을 열고 다음과 같이 수정합니다.

```ts
import { ReportHandler } from "web-vitals";

const reportWebVitals = (onPerfEntry?: ReportHandler) => {
  ...
};

export default reportWebVitals;
```

이렇게 모든 설정이 끝났다면 리액트 프로젝트를 실행시켜 페이지가 잘 표시되는지 확인해보면 됩니다!

#### CRA로 프로젝트 생성과 동시에 Typescript를 설정 (template 사용)

create-react-app에서 제공하는 템플릿 옵션에서 typescript를 적용시켜 생성시킬수도 있습니다.

다음 명령어를 사용해서 새로운 타입스크립트 리액트 프로젝트를 생성해봅시다

```
npx create-react-app my-app --template=typescript
```

이렇게 template 옵션으로 사용하면 전에 [기존-react프로젝트에서-typescript를-설정](#기존-react프로젝트에서-typescript를-설정)에서 했던 것과 동일하게 적용이 된 것을 확인할 수 있고 더 쉽고 빠르게 프로젝트를 생성할 수 있습니다.

---

### 스타일링

리액트는 웹 어플리케이션 개발에 사용하는 라이브러리이므로 스타일링은 물론 웹 페이지 개발과 동일하게 CSS를 사용할 수 있습니다.

자바스크립트 안에서 스타일링 할 수 있는 CSS-in-JS기법을 사용하여 emotion으로 함수형 스타일링도 많이 적용하는 것을 볼 수 있습니다.
(styled-components도 많이 사용하고있다고 하니 관심있으면 찾아보시길)

보통 리액트는 컴포넌트를 기반으로 개발되기에 CSS파일을 갖는 형식으로 스타일을 관리하게 됩니다. 하지만 이렇게 각각의 컴포넌트에서 CSS를 분리하여 관리하다보면 CSS의 클래스명이 중복되어 의도치 않은 스타일이 적용될 수도 있습니다.

#### CSS-in-JS의 장점

이런 문제를 해결하고자 CSS-in-JS라는 방법론이 탄생했는데, 이런 방법으로 사용하면 어떤 장점이 있는지 살펴보자

> **클래스명 버그 해결**

보통 CSS에 클래스명을 생성하고 스타일을 작성한 후 해당 이름을 HTML 태그에 적용함으로써 스타일을 적용합니다. 하지만 이런 방식은 클래스명의 중복, 겹침 또는 오타 같은 문제가 발생할 수도 있기에 CSS-in-JS는 스타일을 컴포넌트에 직접 적용함으로써 이런 문제를 해결하고 있다

> **보다 쉬운 CSS 관리**

CSS-in-JS는 모든 스타일이 특정 컴포넌트에 연결되기 때문에 보다 명확히 사용되는 스타일을 알 수 있으며 불필요한 스타일을 쉽게 제거할 수 있다

> **간단한 동적 스타일 적용**

일반적으로 동적 스타일을 위해 여러 클래스를 생성하고 해당 클래스가 특정 조건일 때에 추가되도록 하는데, 이런 방식은 코드를 복잡하게 하며 깔끔하지 않지만, CSS-in-JS는 여러 클래스를 만들 필요가 없으며 컴포넌트의 상태에 따라 쉽고 직관적으로 동적 스타일을 줄 수 있다

> **CSS 자동 구성**

styled-components 또는 Emotion을 사용하면 페이지에 렌더링되는 컴포넌트를 추적하여 해당 스타일을 완전히 자동으로 추가합니다. 또한 코드 분할(Code Splitting)시 사용자가 필요한 최소한의 코드를 자동으로 추가한다

#### Emotion 스타일링 적용

Emotion으로 스타일링을 하려면 먼저 현재 프로젝트의 터미널로 들어가 다음 명령어를 입력한다

```shell
npm install --save @emotion/react @emotion/styled
```

그러면 간단하게 App.tsx파일을 CSS-in-JS방식으로 수정한다하면

```tsx
import "./App.css";

function App() {
  return (
    <div className="App">
      <header className="App-header">...</header>
    </div>
  );
}

export default App;
```

위와 같은 코드를 아래처럼 변경할 수 있을 것이다.

```tsx
import "./App.css";
import styled from "@emotion/styled";

const Container = styled.div`
  text-align: center;
`;

function App() {
  return (
    <Container>
      <header className="App-header">...</header>
    </Container>
  );
}

export default App;
```

Emotion을 사용하여 리액트 컴포넌트를 생성하기 위해서는 `styled.[HTML태그]`형식과 자바스크립트의 템플릿 리터럴(``)을 사용하면 쉽게 컴포넌트를 스타일링 할 수 있다.

동적인 이미지인 img태그도 아래처럼 변경할 수 있다

```tsx
import styled from "@emotion/styled";

const AppLogo = styled.img`
  height: 40vmin;
  pointer-events: none;

  @media (prefers-reduced-motion: no-preference) {
    animation: App-logo-spin infinite 20s linear;
  }
`;

const AppLink = styled.a`
  color: #61dafb;
`;

function App() {
  return (
    <Container>
      <header className="App-header">
        <AppLogo src={logo} alt="logo" />
        <p>
          Edit <code>src/App.tsx</code> and save to reload.
        </p>
        <link
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </link>
      </header>
    </Container>
  );
}

export default App;
```

여기서, 중요한 점은 @media를 리터럴 안에 적용시킬 수 있다는 점과 원래 css였다면 .App-logo라는 클래스명안에 animation을 적용시켜야했다면

```css
@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}
```

Emotion으로 제작한 컴포넌트는 해당 컴포넌트가 직접 애니메이션을 수행하므로 클래스명을 특별히 지정하지 않고 직접 애니메이션을 사용하면 된다는 것

```tsx
const AppLogo = styled.img`
  height: 40vmin;
  pointer-events: none;

  @media (prefers-reduced-motion: no-preference) {
    animation: App-logo-spin infinite 20s linear;
  }
`;
```

또한, keyframes를 사용하여 로고 이미지에서 사용할 회전 애니메이션을 따로 선언하여 변수로 사용할 수도 있다.

```tsx
import styled from "@emotion/styled";
import { keyframes } from "@emotion/react";

const spinAnimation = keyframes`
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
`;

const AppLogo = styled.img`
  height: 40vmin;
  pointer-events: none;

  @media (prefers-reduced-motion: no-preference) {
    animation: ${spinAnimation} infinite 20s linear;
  }
`;
```

Emotion으로 제작한 컴포넌트는 자바스크립트의 템플릿 리터럴을 사용하기 때문에 문자열 중간에 자바스크립트 변수를 사용할 수도 있다.

이처럼 자주 사용되는 애니메이션은 Emotion의 keyframes를 사용하여 미리 정의하고, 필요한 부분에서 불러와 사용하면 된다.

모든 컴포넌트는 Emotion으로 바꾸면 다음과 같다.

```tsx
import logo from "./logo.svg";
import "./App.css";
import styled from "@emotion/styled";
import { keyframes } from "@emotion/react";

const Container = styled.div`
  text-align: center;
`;

const Header = styled.header`
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
`;

const spinAnimation = keyframes`
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
`;

const AppLogo = styled.img`
  height: 40vmin;
  pointer-events: none;

  @media (prefers-reduced-motion: no-preference) {
    animation: ${spinAnimation} infinite 20s linear;
  }
`;

const AppLink = styled.a`
  color: #61dafb;
`;

function App() {
  return (
    <Container>
      <Header>
        <AppLogo src={logo} alt="logo" />
        <p>
          Edit <code>src/App.tsx</code> and save to reload.
        </p>
        <AppLink
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </AppLink>
      </Header>
    </Container>
  );
}

export default App;
```

---

### 절대경로로 컴포넌트 추가

리액트 프로젝트 개발 시 우리는 수많은 리액트 컴포넌트를 제작하고, 제작한 컴포넌트를 블록을 조합하듯 페이지를 제작하게된다. 이때 리액트 컴포넌트는 보통 상대경로(import Button from './../../../Button')를 사용하여 불러와 사용하게 된다.

이는 컴포넌트의 개수가 적고 폴더 구조가 복잡하지 않을 경우에는 큰 문제가 없다.

하지만 프로젝트가 커지고 수많은 컴포넌트들이 추가되면서 프로젝트의 폴더 구조가 복잡해지면, 상대 경로 추가 방식은 어떤 경로를 지정하고 있는지 명확하게 파악하기 어렵고 필요한 컴포넌트를 추가할 때에 경로를 추가하기 어렵다.

이런 문제는 타입스크립트의 설정으로 간단히 해결할 수 있다.

프로젝트에서 `tsconfig.json`파일을 열고 바음과 같이 baseUrl옵션을 추가한다.

```json
{
  "compilerOptions": {
    ...
    "jsx": "react-jsx",
    "baseUrl": "src"
  },
  ...
}
```

그러면 기존에 상대경로로 import했던 컴포넌트를

```tsx
import App from "./components/App";
```

아래처럼 절대경로로 사용할 수 있게된다.

```tsx
import App from "components/App";
```

지금은 폴더구조가 복잡하지 않아 필요성이 느껴지지 않겠지만, 실무에서 복잡한 프로젝트를 다루게된다면 이런 방식이 왜 필요한지 알게될 것이다.

---

### Prettier

Prettier는 코드 포맷터(Code formatter)로 Javascript, CSS, JSON 등을 지원한다.
Prettier는 미리 약속한 코드 스타일에 맞춰 자동으로 코드의 형식을 수정해주는 도구로, 협업시 여러 개발자들의 코드 스타일을 맞추는데 큰 도움을 준다.

#### Prettier 설치

Prettier를 적용시킬 프로젝트의 터미널을 열고 다음 명령어로 Prettier를 설치한다

```shell
npm install --save-dev prettier
```

#### Prettier 설정

해당 프로젝트의 루트 폴더에 `.prettierrc.js` 파일을 생성하고 다음과 같이 수정하여 Prettier를 설정합니다.

```js
module.exports = {
  singleQuote: true,
  trailingComma: "all",
  printWidth: 100,
};
```

여기서 설정한 내용은 다음과 같다

- **singleQuote** : 싱글쿼트(')를 주로 사용하도록 설정
- **trailingComma** : 콤마(,)를 추가할 수 있다면, 콤마를 추가하도록 설정
- **printWidth** : 한 줄에 작성할 수 있는 최대 코드 문자 수를 설정

#### Prettier 실행

설정이 완료되었다면, package.json파일에서 Prettier를 실행하는 스크립트를 작성한다.

아래처럼 "format"과 "format:fix"라는 스크립트를 추가한다.

```json
{
  ...
  "scripts": {
    ...
    "eject": "react-scripts eject",
    "format": "prettier --check ./src",
    "format:fix": "prettier --write ./src"
  },
  ...
}
```

- format : Prettier를 check 옵션과 함께 실행하여 우리가 설정한 내용에 위반되는 내용이 있는지 검사하는 스크립트
- format:fix : Prettier를 write 옵션과 함께 사용하여 잘못된 내용을 설정한 내용에 맞게 자동으로 수정해주는 스크립트

자 이제 Prettier를 실행해보자

해당 프로젝트에 `.prettierrc.js`파일에 맞는 format을 지키고 있는지 검사하려면 해당 프로젝트 터미널에 다음과 같이 입력한다

```shell
npm run format
```

그러면 다음과 같은 결과를 확인할 수 있다
![image](https://github.com/myeongcode/blog/assets/67165016/8735ba8b-0391-49e1-9f83-5a973340bc97)

결과 내용을 보면 4가지의 파일에서 prettier 규칙에 위반하는 것을 확인할 수 있다.

이제 위반한 내용을 쉽게 수정하게 만들려면 다음 명령어를 실행시키면 된다.

```shell
npm run format:fix
```

![image](https://github.com/myeongcode/blog/assets/67165016/fb7d465e-52a3-4306-b79d-81b88e649ba8)

그리고 나서 다시 `npm run format`을 해보면 문제가 없다는 것을 확인할 수 있다

![image](https://github.com/myeongcode/blog/assets/67165016/8a7f3d45-c2f4-4216-8b84-f561a7f9203f)

---

### ESLint

ESLint는 ES(ECMAScript)와 Lint(에러 코드 표식)의 합성어로, 자바스크립트의 **코드를 분석하고 잠재적인 오류나 버그를 찾는데 도움을 주는 정적 분석 툴**이다

여러 개발자들이 하나의 소스코드를 수정하는 협업 환경에서 ESLint는 소스 코드를 분석하고 오류나 버그의 가능성을 지적하거나 소스 코드의 스타일을 일관성 있게 관리해주기 때문에 Prettier와 함께 자주 사용된다

#### ESLint 설치

ESLint를 설치할 프로젝트의 터미널을 열고 다음과 같이 ESLint를 설치한다

```shell
npm install eslint --save-dev
```

#### ESLint 설정

설치가 됐다면 다음 명령어를 실행하여 ESLint를 초기화하자

```shell
npx eslint --init
```

그리고나서는 7~8개의 질문을 할건데

1. ESLint를 설정하기 위해 필요한 라이브러리를 설치할 것인가? y
2. 문제점을 찾는 것과 잘못된 점을 고치는 스크립트를 따로 작성할 것인가? To check syntax and find problem
3. 프로젝트에서 모듈을 추가할 때 어떤 방식을 선택할건지? Javascript
4. 어떤 프로젝트에서 사용할건지? React
5. Typescript를 사용하는지? Yes
6. 어떤 환경에서 실행되는지? Browser
7. 설정 파일의 포맷을 어떤 형식으로 저장할건지? Javascript
8. 지금까지 설정한 내용으로 설치를 진행할건지? Yes
9. 어떤 패키지 매니저로 설치하는걸 원하는지? npm

![image](https://github.com/myeongcode/blog/assets/67165016/83368548-8dc0-48f1-946f-b7fabd69de3c)

그러면 eslintrc.js파일이 자동으로 생성되고 안에는 다음과 같은 내용이 추가된다.

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react/recommended",
  ],
  overrides: [
    {
      env: {
        node: true,
      },
      files: [".eslintrc.{js,cjs}"],
      parserOptions: {
        sourceType: "script",
      },
    },
  ],
  parser: "@typescript-eslint/parser",
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
  },
  plugins: ["@typescript-eslint", "react"],
  rules: {},
};
```

만약 ESLint와 타입스크립트를 검사하는 룰을 변경하고싶다면, rules 옵션에 필요한 내용을 추가하면 된다.

마지막으로, ESLint에 리액트 버전을 알려줄 필요가 있으며 react/react-in-jsx-scope 규칙의 사용을 중지시킬 필요가 있다.

```js
//eslintrc.js

module.exports = {
  settings: {
    react: {
      version: "detect",
    },
  },
  env: {
    ...
  },
  ...
  rules: {
    "react/react-in-jsx-scope": "off",
  },
};
```

react/react-in-jsx-scope 규칙은 jsx파일에서 import React from 'react'를 항상 사용하도록 하는 규칙이지만 리액트의 버전 17부터 import React from 'react'를 할 필요가 없어졌기 때문에 이 규칙을 사용하지 않도록 할 필요가 있다.

자세한 내용은 아래 공식 문서를 참고하면 된다

> react/react-in-jsx-scope : https://github.com/jsx-eslint/eslint-plugin-react/blob/master/docs/rules/react-in-jsx-scope.md

> Removing Unused React imports : https://legacy.reactjs.org/blog/2020/09/22/introducing-the-new-jsx-transform.html#removing-unused-react-imports

이제 설정한 ESLint를 사용하여 잠재적인 오류나 버그를 찾기 위한 실행 스크립트를 만들어보자.
package.json에서 ESLint 실행 스크립트를 추가하자

```json
{
  ...
  "scripts": {
    ...
    "lint": "eslint ./src",
    "lint:fix": "eslint --fix ./src"
  },
  ...
}
```

#### ESLint 실행

다음과 같이 명령어를 실행하면 ESLint로 소스코드를 검사해볼 수 있다

```shell
npm run lint
```

현재는 오류가 발생하지 않았지만, eslint로 인한 규칙 위반시 `npm run lint:fix` 명령어를 실행하면 된다.

---

## 요약

우리가 배운 내용을 간단하게 요약하면 다음과 같다

1. **CRA에서 template으로 Typescript 간단하게 적용시키기**
2. **Emotion으로 CSS-in-JS 함수형 스타일링하여 컴포넌트 제작하기**
3. **소스코드의 스타일을 맞추거나 잠재적인 오류, 버그를 방지하기 위해 실무에서 자주 사용되는 Prettier와 ESLint 적용 방법**

실무에서 다른 개발자들과 협업하기 위해서는 꼭 필요하고 자주 사용된다고 하니 알아놓으면 좋을 것 같고, 앞으로 프로젝트 초기설정을 할 때에는 위에서 배운 내용을 토대로 쉽게 셋팅할 수 있을 것 같다.
