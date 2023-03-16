# 🤩 JSX

## JSX란?

* 자바스크립트의 표준 규격인 ECMAScript에 XML을 추가한 문법 확장이라고 생각하면 된다.
* React.createElement(component, props, ...children) 함수를 제공한다.
* 작성된 XML을 React.createElement 코드로 변환 시켜준다.

```jsx
//JSX 코드
<p>Hello World!</p> 

// 변환된 JS 코드
React.createElement('p',null,"Hello World");
```

{% hint style="info" %}
HTML에서는 input, br등 태그를 사용할 때 "/" 를 사용하여 태그를 닫아주지 않아도 됐지만 JSX에서는 태그를 무조건 닫아줘야한다.
{% endhint %}

## JSX 코드가 JS(React.createElement)코드로 변환된 예제

[Babel 공식 홈페이지](https://babeljs.io/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie\_mob%2011\&build=\&builtIns=false\&corejs=3.21\&spec=false\&loose=false\&code\_lz=Q\&debug=false\&forceAllTransforms=false\&modules=false\&shippedProposals=false\&circleciRepo=\&evaluate=false\&fileSize=false\&timeTravel=false\&sourceType=module\&lineWrap=true\&presets=env%2Creact%2Cstage-2\&prettier=false\&targets=\&version=7.21.2\&externalPlugins=\&assumptions=%7B%7D)에서 **JSX 작성한 코드가 React.createElement 코드로 변환**하는 것을 확인 할 수 있다.\
**Presets에서 react를 체크**하거나, **Plugins에서 @babel/plugin-transform-react-jsx를 추가**하면 JSX를 실험할 수 있다.

**문법 -** React.createElement(component, props, ...children)&#x20;

### Example 1

```jsx
// JSX 코드
<p>Hello World!</p>

// 변환된 JS 코드
React.createElement("p", null, "Hello World!");
```

### Example 2

```jsx
// JSX 코드
<Greeting name='world'/>

// 변환된 JS 코드
React.createElement(Greeting, {
  name: "world"
});
```

### Example3

```jsx
// JSX 코드
<Button type='button'>send</Button>

// 변환된 JS 코드
React.createElement(Button, {
  type: "button"
}, "send"));
```

### Example4

```jsx
// 자식요소가 포함되있을때의 JSX 코드 
<div className="test">
  <p>Hello World!</p>
  <Button type='button'>send</Button>
</div>

// 변환된 JS 코드
React.createElement("div", {
  className: "test"
}, React.createElement("p", null, "Hello World!"),React.createElement(Button, {
  type: "button"
}, "send"));
```

### Example5

```jsx
// 마우스 이벤트, 변수를 사용하는 JSX코드
<div>
  <p>Count : {count}!</p>
  <button type='button' onClick={()=>setCount(count+1)}>Increase</button>
</div>

// 변환된 JS 코드
React.createElement("div", null, React.createElement("p", null, "Count : ", count, "!"), React.createElement("button", {
  type: "button",
  onClick: () => setCount(count + 1)
}, "Increase"));
```

### Example6

```jsx
// 컴포넌트 작성 코드
function Greeting({name}){
    return (
        <p>Hello, world!</p>
    )
}

// 변환된 JS 코드
function Greeting({
  name
}) {
  return React.createElement("p", null, "Hello, world!");
}
```

## JSX 이해하기

* React를 사용할 때 JSX는 필수가 아니다.
* 빌드 환경에서 컴파일 설정 하고 싶지 않을때 JSX를 사용하지 않고 순수 JavaScript로 React를 만들면 된다.
