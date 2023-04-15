# 😰 React의 Hook

### **React Hooks 이란?**

* React 16.8부터 새로 도입된 기능이다.
* Hook은 props, state, context, refs, 그리고 lifecycle와 같은 **React 개념을 좀 더 직관적으로 제공한다**.
* Hook을 사용하면 기존 Class 사용한 코드를 작성할 필요가 없고 상태 값과 여러 React의 기능을 사용할 수 있습니다
* **선택적 사용**
  * 기존의 코드를 다시 작성할 필요 없이 일부의 컴포넌트들 안에서 Hook을 사용 할 수 있다.

### **Hook 사용 규칙**

* **반복문, 조건문, 중첩된 함수 내에서 사용이 불가**하며 **최상위 에서만 Hook을 호출**해야한다.&#x20;
* **React 함수 컴포넌트** 내에서만 Hook을 호출해야 한다.

### **대표적인 Hooks의 종류**&#x20;

*   useState

    * 상태 유지 값과 그 값을 갱신하는 함수를 반환한다.

    <pre class="language-javascript"><code class="lang-javascript"><strong>const [state, setState] = useState(initialState);
    </strong></code></pre>
* useEffect
  * useEffect 는 React component가 렌더링 될 때마다 특정 작업(Sied effect)을 실행할 수 있도록 하는  Hook이다.
  * 컴포넌트가 렌더링 될 때 특정 작업을 실행할 수 있도록 하는 Hook이다.
  * 클래스형 컴포넌트에서는 생명주기 메소드를 사용할 수 있었는데, 이를 함수형 컴포넌트에서도 사용 할 수 있게 되었다.

타이머 예제

React의 외부에 우아하게 접근. 이 정도는 useEffect를 안 쓴다고 크게 문제가 되지 않지만, 이렇게 쓰는 습관을 들이자.

```jsx
useEffect(() => {
	document.title = `Now: ${new Date().getTime()}`;
});
```

타이머를 on/off하는 기능을 그냥 만들면 문제가 발생한다.

* 현재 timer 함수는 컴포넌트가 언마운트시 setInterval을 종료하는 로직이 존재하지 않아 setInterval 함수가 계속 돌아가는 문제가 있다.

```jsx
function Timer() {
	useEffect(() => {
		setInterval(() => {
			document.title = `Now: ${new Date().getTime()}`;
		}, 100);
	});

	return (
		<p>Playing</p>
	);
}

export default function TimerControl() {
	const [playing, setPlaying] = useState(false);
	
	const handleClick = () => {
		setPlaying(!playing);
	};

	return (
		<div>
			{playing ? (
				<Timer />
			) : (
				<p>Stop</p>
			)}
			<button type="button" onClick={handleClick}>
				Toggle
			</button>
		</div>
	);
}
```

#### 언마운트 처리&#x20;

* 컴포넌트 언마운트 시 특정 코드를 실행 시키고 싶을때 useEffect는 return() => {} 화살표 함수안에 코드를 작성하면 된다.

```jsx
useEffect(() => {
	const savedTitle = document.title;

	const id = setInterval(() => {
		document.title = `Now: ${new Date().getTime()}`;
	}, 100);

	return () => {
		document.title = savedTitle;
		clearInterval(id);
	};
});
```

#### 처음 렌더링 시 사용 법&#x20;

의존성 배열에서 아무 것도 지정하지 않으면  한번만 실행한다.

주로 API를 호출해서 데이터를 얻을 때 사용한다.

```javascript
useEffect(()=>{
    ...
},[])
```



* useContext

## useLayoutEffect

**useEffect**와 매우 유사하지만, 조금 더 일찍 실행되어 DOM이 업데이트되기 전에 실행되는 차이점이 있습니다

* useEffect와 동일한 기능을 제공하지만, useEffect가 컴포넌트가 렌더링된 후에 비동기적으로 실행되는 반면, useLayoutEffect는 DOM 업데이트 전에 동기적으로 실행됩니다. 이로 인해 렌더링 결과를 동기적으로 확인할 수 있습니다.
* useLayoutEffect는 useEffect와 비슷한 문법을 가지며, useEffect와 동일한 2개의 인수를 받습니다. 첫 번째 인수는 부수 효과 함수이고, 두 번째 인수는 의존성 배열입니다. useLayoutEffect는 useEffect와 마찬가지로 부수 효과 함수를 반환합니다.
*   일반적으로 useEffect를 사용하여 대부분의 상황에서 충분합니다. 그러나 렌더링된 DOM을 변경해야 하는 상황에서 useLayoutEffect가 더 적합합니다. useLayoutEffect를 사용하여 DOM 노드를 조작하면 레이아웃 계산을 수행하기 전에 변경 사항이 적용됩니다. 이로 인해 화면 깜박임이나 레이아웃 재계산 문제를 해결할 수 있습니다.

    \


## React StrictMode

React v16.3 에서 도입된 개발도구이다.&#x20;

* 이 모드를 사용하면 애플리케이션을 엄격한 모드로 실행하여 개발자가 더 많은 경고와 에러를 볼 수 있다&#x20;
* 부적절한 사용 방지 : 경고 메시지를 통해 부적절한 사용 방지를 돕는다.
* 숨겨진 문제 찾기 : 숨겨진 문제를 찾기 위한 강화된 도구를 제공한다.
* 앱 성능 개선 : 컴포넌트 수명주기를 좀 더 엄격하게 검사하여 앱의 성능을 개선할 수 있다.

&#x20;
