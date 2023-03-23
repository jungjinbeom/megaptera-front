# 😁 React State

## Thinking in React

* step 3. Find the minimal but complete representation of UI state\
  : 최소한이지만 UI 상태 표현 완성하기
* step 4. Identify where your state should live\
  : 상태가 어디서 살아있어야하는지 식별하기
* step 5. Add inverse data flow\
  : 역데이터 흐름 추가하기

### React의 State

* React의 변경을 다루기 위한 요소&#x20;
* state가 변경되면 해당 컴포넌트와 하위 컴포넌트를 리렌더링한다.
* DRY(Don\`t Repeat Yourself) 중복 배제&#x20;
* SSOT 단일 진실 공급원

## Inverse Data Flow

### Inverse Data Flow란 ?&#x20;

> 하위 컴포넌트의 props로 함수를 전달, 흔히 콜백 함수라고 한다.

* TypeScript(정확히는 JavaScript)는 함수가 일급(first-class) 객체다. 즉, 어떤 함수를 다른 함수에 인자로 넘겨주거나, 어떤 함수를 리턴 값으로 사용할 수 있다. 익명 함수, 클로저 등과 함께 사용하면 시너지가 큼.
  * [일급 함수](https://developer.mozilla.org/ko/docs/Glossary/First-class\_Function)
  * 다시 [“Lifting State Up”](https://ko.reactjs.org/docs/lifting-state-up.html)

## 일급 객체

### 일급객체란?

> 일급객체란 다른 객체들에게 적용 가능한 연산을 모두 지원하는 객체를 말한다.
>
>>

* 변수에 할당 할 수 있어야 한다.

```javascript
const mul = function (num) {
  return num*num;
}
```

* 다른 함수를 인자로 전달 받는다.

```javascript
function mul(num) {
  return num*num;
}

// func는 매개변수임, 이름은 아무거나 지정해도 상관없음
function mulNum(func, number) {
  return func(number);
}

let result = mulNum(mul, 3); 
```

* 객체의 리턴 값으로 리턴 할 수 있어야 한다.

```javascript
function add(num1) {
  return function (num2) {
    return num1 + num2;
  }
}

add(3)(4); // 7
```



### 일급 객체의 이점

> 고차함수(Higher order function)를 만들 수 있다.
>
> 콜백(callback)을 사용할 수 있다

## Lifting State Up

### Lifting State Up란?

> 컴포넌트 간에 상태를 공유하기 위해 상위 컴포넌트로 상태를 끌어올리는 것



