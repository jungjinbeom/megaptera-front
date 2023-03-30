# 😶 Fetch API & CORS

### Fetch API&#x20;

* **Fetch API란?**
  * HTTP 파이프라인을 구성하는 요청과 응답등의 요소를 JavaScript에서 접근하고 조작할 수 있는 인터페이스를 제공한다.
  * fetch() 함수는 웹브라우저에서 URL 요청을 전송할 때 전역 스코프를 가지기 때문에 어디서든 사용이 가능하다.
* **fetch 사용법**
* **fetch()**
  * **첫 번째 인수는 필수값으로  url값을 받는다.**&#x20;
  * **두 번째 인수인 options는 HTTP 요청 방식, 요청 헤더, 요청 본체**등 설정이 가능하다.

```javascript
fetch(url, options)

fetch(url, (options))
  .then((res)=> {
    //url로부터 fetch의 호출이 성공했을 때의 동작
  })
  .catch((error)=>{
    //url로부터 fetch의 호출이 실패했을 때의 동작
  });
  
  //메소드 설정 예시 
  const response = fetch(url, {
	method: 'POST',
});
```

```javascript
fetch('http://localhost:3000/products');
// → Promise

await fetch('http://localhost:3000/products');
// → Response

const response = await fetch('http://localhost:3000/products');
// → response.body는 ReadableStream

const reader = response.body.getReader();

const chunk = await reader.read();
// → chunk.value는 Uint8Array 타입.
// → 원래는 chunk.done이 true일 때까지 반복해야 한다.

const body = new TextDecoder().decode(chunk.value);

const data = JSON.parse(body);
```

**JSON을 기본으로 지원한다.**

```javascript
const response = await fetch('http://localhost:3000/products');
const data = await response.json();
```



### ReableStream

* Streams API의 ReableStream 인터페이스는 바이트 데이터를 읽을 수 있는 스트림을 제공한다.
* Fetch API는 Response 객체의 body 속성을 통하여 ReableStream의 구체저긴 인스턴스를 제공한다.

### 학습 키워드

### Promise

* **Promise란?**
  * 자바스크립트 **비동기 처리에 사용되는 객체**이다.
  * **비동기 처리란** 특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 자바스크립트의 특성&#x20;
* **Promise는 왜 필요한가?**
  * Promise는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용된다.
  * 자바스크립트는 비동기 처리를 위한 하나의 패턴으로 콜백함수를 사용한다. **콜백패턴은 콜백 헬로 인해 가독성이 매우 떨어지고 발생한 에러의 처리가 곤란하며 비동기 처리에도 한계가 있다**.
  * ES6에서는 비동기 처리를 위한 **또 다른 패턴으로 프로미스는 콜백패턴이 가지 단점을 보안, 비동기 처리 시점을 명확하게 표현이 가능하다.**
* **Promise의 3가지 상태**&#x20;
  * Pending(대기)
    * 비동기 처리 로직이 아직 완료되지 않은 상태
  * Fulfilled(이행)
    * 비동기 처리가 완료되어 프로미스 결과 값을 반환해준 상태
  * Rejected(실패)
    * 비동기 처리가 실패하거나 오류가 발생한 상태

### CORS 란?

* 교차 출처 리소스 공유 (Cross-Origin Resource Sharing), 웹브라우저가 가지고 있는 보안 정책
* 추가 HTTP 헤더를 사용하여, **한 출처에서 실행중인 웹 애플리케이션이 다른 출처의 선택한 자원에 접근할 수 있는 권한을 부여하도록 브라우저에 알려주는 체제**이다.
* 웹 브라우저는 **동일 출처 정책(same-origin policy)**에 따라 웹 페이지와 리소스를 요청한 곳(여기서는 REST API 서버)이 서로 다른 출처(포트까지 포함)일 때 서버에서 얻은 결과를 사용할 수 없게 막는다.&#x20;
* 서버에 요청하고 응답을 받아오는 것까지는 이미 진행이 다 된 상황이란 점을 인지하자

**해결방법**&#x20;

* REST API 서버에서 Headers에 "Acces-Control-Allow-Origin" 속성을 추가한다
* Express에서는 CORS 미들웨어를 설치해서 사용한다.

**Express CORS 설정**

패키지 설치

```bash
npm i cors
npm i -D @types/cors
```

CORS 미들웨어 사용

```typescript
import express from 'express';
import cors from 'cors';

const app = express();

app.use(cors());
```

