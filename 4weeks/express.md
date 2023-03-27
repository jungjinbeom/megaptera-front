---
description: 1. 용어의 정의(정확한 정의) 2. 역사 또는 왜 필요한가/왜 생겼는가 3. 특징 (또는 장/단점) 4. 실제 사용 사례나 경험
---

# 😒 Express

### Express 셋팅&#x20;

프로젝트 폴더 생성 후 폴더에 접근&#x20;

```sh
mkdir express-demo-app
cd mkdir express-demo-app

```

.gitignore 파일 생성 후 비활성화 할 목록 추가&#x20;

```sh
touch .gitignore
echo "/node_modules/" > .gitignore
```

패키지 생성&#x20;

```sh
npm init -y
```

TypeScript + ESLint 설치 및 초기셋팅

```sh
npm i -D typescrit
npx tsc --init

npm i -D eslint
npx eslint --init
```

ts-node 설치

```
npm i -D ts-node
```

Express 설치

```
npm i express 
npm i -D @types/express
```

### Express 예제

app.ts 파일 생성&#x20;

```sh
touch app.ts 
```

```typescript
import experss from 'express';
const port = 300
```

### 학습 키워드

*   Express 란

    * Node.js를 위한 빠르고 개방적인 간결한 웹 프레임워크이며 웹 애플리케이션API 개발을 위해 설계되었다.



    * Node.js는 JavaScript로 브라우저가 아니라 서버를 구축하고 , 서버에서 JavaScript가 작동되도록 해주는 런타임 환경이다. Express는 이런 Node.js의 원칙과 방법을 이용하여 웹애플리케이션을 만들기 위한 프레임워크이며 사실상 Node.js의 표준 웹서버 프레임워크로 불려질 만큼 많이 사용 중이다.&#x20;
* Express를 사용하는가?
  * Express는 프레임워크이며 웹 애플리케이션을 만들기 위한 각종 라이브러리와 미들웨어등이 내장되어 있어 개발하기 편하다.
* Expressa의 특징&#x20;
  * 수많은 개발자들에게 개발 규칙을 강제하여 코드 및 구조의 통일성을 향상시킬 수 있다.&#x20;
  * 가장 많이 보편적으로 사용되기 때문에 구글링을 통해 충분한 래퍼런스를 검색할 수 있다.
  * 웹서버를 빠르게 구현하기 위해 개발시에 구조에 대한 자유도가 높다.
  * TypeScript를 express에서 사용 할 수 있지만, tsconfig.json, lint.json 등의 세팅 과정이 복잡하다.





* node-mon
* URL 구조
* REST API
* HTTP Method(CRUD)
