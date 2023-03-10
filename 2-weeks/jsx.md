# ๐คฉ JSX

## JSX๋?

* ์๋ฐ์คํฌ๋ฆฝํธ์ ํ์ค ๊ท๊ฒฉ์ธ ECMAScript์ XML์ ์ถ๊ฐํ ๋ฌธ๋ฒ ํ์ฅ์ด๋ผ๊ณ  ์๊ฐํ๋ฉด ๋๋ค.
* React.createElement(component, props, ...children) ํจ์๋ฅผ ์ ๊ณตํ๋ค.
* ์์ฑ๋ XML์ React.createElement ์ฝ๋๋ก ๋ณํ ์์ผ์ค๋ค.

```jsx
//JSX ์ฝ๋
<p>Hello World!</p> 

// ๋ณํ๋ JS ์ฝ๋
React.createElement('p',null,"Hello World");
```

* HTML์์๋ input, br๋ฑ ํ๊ทธ๋ฅผ ์ฌ์ฉํ  ๋ "/" ๋ฅผ ์ฌ์ฉํ์ฌ ํ๊ทธ๋ฅผ ๋ซ์์ฃผ์ง ์์๋ ๋์ง๋ง JSX์์๋ ํ๊ทธ๋ฅผ ๋ฌด์กฐ๊ฑด ๋ซ์์ค์ผํ๋ค.
* ์ค๊ดํธ๋ฅผ ์ฌ์ฉํ์ฌ JavaScript ์ฝ๋๋ฅผ ์ฌ์ฉํ  ์ ์๋ค.

## JSX ์ฝ๋๊ฐ JS(React.createElement)์ฝ๋๋ก ๋ณํ๋ ์์ 

[Babel ๊ณต์ ํํ์ด์ง](https://babeljs.io/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie\_mob%2011\&build=\&builtIns=false\&corejs=3.21\&spec=false\&loose=false\&code\_lz=Q\&debug=false\&forceAllTransforms=false\&modules=false\&shippedProposals=false\&circleciRepo=\&evaluate=false\&fileSize=false\&timeTravel=false\&sourceType=module\&lineWrap=true\&presets=env%2Creact%2Cstage-2\&prettier=false\&targets=\&version=7.21.2\&externalPlugins=\&assumptions=%7B%7D)์์ **JSX ์์ฑํ ์ฝ๋๊ฐ React.createElement ์ฝ๋๋ก ๋ณํ**ํ๋ ๊ฒ์ ํ์ธ ํ  ์ ์๋ค.\
**Presets์์ react๋ฅผ ์ฒดํฌ**ํ๊ฑฐ๋, **Plugins์์ @babel/plugin-transform-react-jsx๋ฅผ ์ถ๊ฐ**ํ๋ฉด JSX๋ฅผ ์คํํ  ์ ์๋ค.

### Example 1

```jsx
// JSX ์ฝ๋
<p>Hello World!</p>

// ๋ณํ๋ JS ์ฝ๋
React.createElement("p", null, "Hello World!");
```

### Example 2

```jsx
// JSX ์ฝ๋
<Greeting name='world'/>

// ๋ณํ๋ JS ์ฝ๋
React.createElement(Greeting, {
  name: "world"
});
```

### Example3

```jsx
// JSX ์ฝ๋
<Button type='button'>send</Button>

// ๋ณํ๋ JS ์ฝ๋
React.createElement(Button, {
  type: "button"
}, "send"));
```

### Example4

```jsx
// ์์์์๊ฐ ํฌํจ๋์์๋์ JSX ์ฝ๋ 
<div className="test">
  <p>Hello World!</p>
  <Button type='button'>send</Button>
</div>

// ๋ณํ๋ JS ์ฝ๋
React.createElement("div", {
  className: "test"
}, React.createElement("p", null, "Hello World!"),React.createElement(Button, {
  type: "button"
}, "send"));
```

### Example5

```jsx
// ๋ง์ฐ์ค ์ด๋ฒคํธ, ๋ณ์๋ฅผ ์ฌ์ฉํ๋ JSX์ฝ๋
<div>
  <p>Count : {count}!</p>
  <button type='button' onClick={()=>setCount(count+1)}>Increase</button>
</div>

// ๋ณํ๋ JS ์ฝ๋
React.createElement("div", null, React.createElement("p", null, "Count : ", count, "!"), React.createElement("button", {
  type: "button",
  onClick: () => setCount(count + 1)
}, "Increase"));
```

### Example6

```jsx
// ์ปดํฌ๋ํธ ์์ฑ ์ฝ๋
function Greeting({name}){
    return (
        <p>Hello, world!</p>
    )
}

// ๋ณํ๋ JS ์ฝ๋
function Greeting({
  name
}) {
  return React.createElement("p", null, "Hello, world!");
}
```

## JSX ์ดํดํ๊ธฐ

* React๋ฅผ ์ฌ์ฉํ  ๋ JSX๋ ํ์๊ฐ ์๋๋ค.
* ๋น๋ ํ๊ฒฝ์์ ์ปดํ์ผ ์ค์  ํ๊ณ  ์ถ์ง ์์๋ JSX๋ฅผ ์ฌ์ฉํ์ง ์๊ณ  ์์ JavaScript๋ก React๋ฅผ ๋ง๋ค๋ฉด ๋๋ค.
