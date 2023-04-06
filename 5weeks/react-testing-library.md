# 😶 React Testing Library

## React Testing Library

### React Testing Library란?

* 페이스북에서 공식적으로 사용을 권장하는 리액트 테스트 도구이다.
* 사용자가 컴포넌트를 사용하는 것처럼 테스트 할 수 있게 설계되어있다.&#x20;

### 사용예제

**UI 및 컴포넌트의 인터페이스를 테스트 할 수 있는 테스트 코드이다.**\
처음 **테스트 코드 작성 시 label 같이 범용적으로 사용할 수 있는 값을 사용하지 않아 문제**가 됐다.(현재는 추가)\
개발을 진행하면서 이런 문제를 발견할 수 도 있고 **테스트 혹은 테스트 코드를 빠르게 작성했다면 작성 전 또는 작성 직후에 바로 문제를 발견해서 수정이 가능할 것이다. 하지만 시간이 지나면 해당 코드에 대한 지식이 감소하기 때문에 건드리기 힘든 코드가 되기 십상**이다.

```typescript
import { render, screen } from '@testing-library/react';

import TextField from './TextField';

test('TextField', () => {	
	const text = 'Tester';
	const setText = () => {
		// do nothing...
	};

	render((	
		<TextField
			label="Name"
			placeholder="Input your name"
			text={text}
			setText={setText}		
		/>
	));
	
	screen.getByLabelText('Name');
});

```

BDD 스타일로 변경한 코드이다.

* 반복되는 코드를 Extract Function하고, fireEvent등을 통해 인터랙션만 검증하도록 작성했다.

```typescript


import { render, screen, fireEvent } from '@testing-library/react';

import TextField from './TextField';

const context = describe;

describe('TextField', () => {
	const text = 'Tester';
	const setText = jest.fn();
	
	beforeEach(() => {
		setText.mockClear();
		// 또는 jest.clearAllMocks();	
	});
	
	function renderTextField() {
		render((
			<TextField
				label="Name"
				placeholder="Input your name"
				text={text}
				setText={setText}
			/>
		));
	}
	
	it('renders an input control', () => {
		renderTextField();

		screen.getByLabelText('Name');
	});
	
	context('when user types text', () => {	
		it('calls the change handler', () => {
			renderTextField();

			fireEvent.change(screen.getByLabelText('Name'), {
				target: {
					value: 'New Name',
				},
			});
	
			expect(setText).toBeCalledWith('New Name');
		});
	});
```

외부 의존성이 큰 코드를 작성 시, 해당 부분만 가짜로 구현이 가능하다.

```typescript
import { render, screen } from '@testing-library/react';

import App from './App';

jest.mock('./hooks/useFetchProducts', () => () => [
	{
		category: 'Fruits', price: '$1', stocked: true, name: 'Apple',
	},
]);

test('App', () => {
	render(<App />);

	screen.getByText('Apple');
});
```

{% hint style="info" %}
일반적으론 백엔드와 소통하는 부분이 차지하는 비중이 큰데, 이 부분을 하나씩 가짜 구현으로 바꾸다 보면 어려울 때가 있다. 이럴 땐 **MSW 등 다른 대안을 고려**해 보자
{% endhint %}

## given - when - then 패턴&#x20;

### given - when - then 패턴이란?

* 테스트 시나리오를 작성할때 주로 사용하는 패턴이다.

| 키워드        | 설명                                                              |
| ---------- | --------------------------------------------------------------- |
| **given**  | <p>주어진 조건에 대한 코드를 작성한다. <br>테스트할 데이터나 컴포넌트를 초기화하는 로직이 들어간다.</p> |
| **when**   | 테스트할 행동에 대한 코드를 작성한다.                                           |
| **then**   | 테스트 검증 로직에 대해서 작성한다.                                            |



## Mocking

### Mocking이란?

* 단위 테스트를 작성할 때, 해당 코드가 의존하는 부분을 가짜로 대체하는 기법이다&#x20;
