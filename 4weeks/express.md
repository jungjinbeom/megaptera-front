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

### **Express**&#x20;

*   **Express 란?**

    * Node.js를 위한 빠르고 개방적인 간결한 웹 프레임워크이며 웹 애플리케이션API 개발을 위해 설계되었다.



    * Node.js는 JavaScript로 브라우저가 아니라 서버를 구축하고 , 서버에서 JavaScript가 작동되도록 해주는 런타임 환경이다. Express는 이런 Node.js의 원칙과 방법을 이용하여 웹애플리케이션을 만들기 위한 프레임워크이며 사실상 Node.js의 표준 웹서버 프레임워크로 불려질 만큼 많이 사용 중이다.&#x20;
* **왜 Express를 사용하는가?**
  * Express는 프레임워크이며 웹 애플리케이션을 만들기 위한 각종 라이브러리와 미들웨어등이 내장되어 있어 개발하기 편하다.
*   **Express의 특징**&#x20;

    * 수많은 개발자들에게 개발 규칙을 강제하여 코드 및 구조의 통일성을 향상시킬 수 있다.&#x20;
    * 가장 많이 보편적으로 사용되기 때문에 구글링을 통해 충분한 래퍼런스를 검색할 수 있다.
    * 웹 서버를 빠르게 구현하기 위해 개발 시에 구조에 대한 자유도가 높다.
    * TypeScript를 express에서 사용 할 수 있지만, tsconfig.json, lint.json 등의 세팅 과정이 복잡하다.



### URL

* **URL 구조**
  * <mark style="color:red;">https</mark>://<mark style="color:blue;">pangpang.com</mark>/<mark style="color:yellow;">products/2023</mark>?<mark style="color:green;">number=500</mark>
  * <mark style="color:red;">프로토콜</mark>//<mark style="color:blue;">호스트주소:포트번호</mark>/<mark style="color:yellow;">경로</mark>?<mark style="color:green;">쿼리</mark>
  * **프로토콜**&#x20;
    * 컴퓨터끼리 네트워크 통신을 할 때 규격
    * &#x20;Http, Https, FTP, Telnet 등이 있다.
  * **호스트 주소**&#x20;
    * 호스트 명은 **네트워크에 연결된 장치 또는 서버들에 부여되는 고유한 이름**으로 **IP주소나 MAC 주소**와 같은 기계적인 이름을 대신한다.
  * **포트 번호**&#x20;
    * 컴퓨터에서 실행되고 있는 수많은 프로세스들의 주소
    * 기본적으로 포트번호를 입력하지 않았을 때 프로토콜이 가지고 기본적인 포트 번호가 적용된다.
    * HTTP => 80, HTTPS => 443
    * 예시 => [https://www.naver.com ](https://www.naver.com)=> [https://www.naver.com](https://www.naver.com):443
  * **경로**&#x20;
    * 서버 프로그램 내에 짜인 로직으로 가는  영역이다.
    * 보통 개발 되있는 서버의 각 경로에 맞춰 코드를 작성한다.
  * **쿼리**&#x20;
    * URL의 마지막 구성 요소로 query(쿼리)가 있다.
    * 추가적인 데이터를 표현할때 사용한다.
    * query는 path 뒤에 ?를 기점으로 key=value 형태로 데이터를 표현한다.
    * &#x20;예시 => [https://www.youtube.com/watch?v=nHk-AdY1588 ](https://www.youtube.com/watch?v=nHk-AdY1588)

### **REST API**

* **REST API란?**
  * 두 개의 컴퓨터가 인터넷을 통해 정보를 안전하게 교환하기위해 사용하는 인터페이스&#x20;
  * **REST란?**
    * API 작동방식에 대해 존건을 부과하는 소프트웨어 아키텍쳐이다 .
    * 인터넷과 같은 복잡한 네트워크에서 통신을 관리하기 위해 지침으로 만들어졌다.
  * **API란?**
    * 다른 소프트웨어 시스템과 통신하기 위해 따라야 하는 규칙
  * **REST의 구성**&#x20;
    * 자원(Resource) - URI
      * 모든 자원은 고유의 URI(URL)을 가지며 클라이언트는 이 URI를 지정하여 해당 자원에 대해 CRUD명령을 수행할 수 있다.
    * 행위(Verb) - HTTP method
      * 클라이언트가 HTTP method를 사용하여 서버에 수행해야 할 동작을 지정하고 요청하는 방법&#x20;
      * HTTP method에는 GET, POST, PUT/PATCH, DELETE 있다.
        * GET: 서버로부터 리소스 조회
        * POST: 서버에 리소스 생성
        * DELETE: 서버에서 리소스 삭제
        * PUT: 서버에 리소스 수정
    * 표현(Representations)
      * 서버의 행위에 대한 응답(Ex: SON,XML)
  * **REST API 장/단점**
  * **장점**
    * HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.
    * HTTP 프로토콜의 표준을 최대한 활용하여여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
    * 서버와 클라이언트의 역할을 명확하게 분리한다.
  * **단점**
    * 사용할 수 있는 메소드가 한정적이다&#x20;
    * 구형 브라우저가 아직 제대로 지원해주지 못하는 부분이 있다&#x20;

