# 😤 useRef & Custom Hook

### useRef

### useRef란?

* 리액트에서 제공하는 hook 이다
* 컴포넌트의 생애주기 전체에 걸쳐서 유지되는 객체. 즉, 컴포넌트가 없어질 때까지 동일한 객체가 유지된다.
* 값을 참조하기 위한 객체이며 언제든지 값을 변경 할 수 있다.

### useRef 특징

* useRef는 값이 바뀌어도 렌더링에 영향을 주지 않는다.

### useRef 사용용도

* 컴포넌트 안에서 조회 및 수정 할 수 있는 변수를 관리
* 외부 라이브러리를 사용하여 생성된 인스턴스
* Scroll 위치
* 비동기 상황에서 현재 값을 사용하는 경우

**useRef 사용 예제**

비동기 상황에서의 useRef 사용법&#x20;

```typescript
const query = useRef('');
const [filterText, setFilterText] = useState<string>('');

// 실제로 이렇게 사용할 일은 거의 없습니다.
useEffect(() => {
  query.current = filterText;
}, [filterText]);

useEffect(() => {
  setTimeout(() => {
    console.log(query.current);
  }, 5_000);
}, []);
// 현재 값을 나타낼 수 있습니다.
```



**Custom hook**

**Custom hook란?**

* **Custom hook란 React에** 내장되있는 **hook(useState,useEffect)등**을 사용하여 **반복되는 로직을 재사용** 할수 있게 제작이 가능한 함수를 말한다.

**Custom hook 특징**

* "**use"로 시작하는 camelCase로 함수명**을 짓는다.
* Custom hook은 재사용이 가능해 반복되는 코드 수를 줄일 수 있다.
* **관심사 분리**가 가능해진다.
  * 컴포넌트는 비즈니스 로직의 작성하는 영역, JSX를 작성하는 영역이 있다.&#x20;
  * 비즈니스 로직, JSX 작성이 길어지면 가독성에 문제가 생기게 된다. 이러한 문제를 해결하기 위해 **코드는 단위 별로 하나의 관심사만 갖도록 하고 그 관심사에 대해서만 충실히 동작하도록 만들어야 한다.**&#x20;
  * **Custom hook을 작성하여** 비즈니스 로직, JSX 영역의 **관심사에 따라 코드를 분리한다.**

**Custom hook 사용예제**

API를 호출하고  response 값을 반환해주는 로직의 Custom hook이다

```typescript
function useFetchProducts() {
 const [products, setProducts] = useState<Product[]>([])
useEffect(() => {
	const fetchProducts = async () => {
		const url = 'http://localhost:3000/products';
		const response = await fetch(url);
		const data = await response.json();
		setProducts(data.products);
	};

	fetchProducts();
}, []);

return products;
```

## 키워드&#x20;

### 관심사 분리&#x20;

**관심사 분리란?**

* 컴퓨터 프로그램을 구별된 부분으로 분리시키는 디자인 원칙
* 하나의 함수, 변수, 클래스, 컴포넌트에게 한번에 너무 많은 일(concerns)을 부여하게 되면 그 코드를 읽는 사람은 혼란스러울 수 있다. 이러한 해결방법은 **한번에 한 가지 걱정만 하도록 단위를 잘게 나누는 것**이다. 즉, **코드는 단위 별로 하나의 관심사만 갖도록 하고 그 관심사에 대해서만 충실히 동작하도록 만들어야 한다.**

**관심사 분리의 장점**

* 코드가 더욱 명료해짐
* 코드 재사용성이 올라감
* 유지 보수가 용이함
* 테스트 코드 작성이 쉬워진다.
