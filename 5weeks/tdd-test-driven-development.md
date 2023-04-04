# 😌 TDD(Test Driven Development)

### 학습 키워드

## TDD(Test Driven Development) - 테스트 주도 개발

* [테스트 주도 개발](https://github.com/ahastudio/til/blob/main/agile/test-driven-development.md)
* [TDD FAQ](https://github.com/ahastudio/til/blob/main/blog/2016/12-03-tdd-faq.md)
* [Jest를 이용한 간단한 TDD 예제](https://github.com/ahastudio/til/blob/main/jest/20201204-simple-tdd-example.md)

### TDD란

* Test Driven Development의 약자로 **테스트 주도 개발**이라고 한다.
* **반복 테스트를 이용한 소프트웨어 방법론**으로 작은 단위의 테스트 케이스를 작성하고 이를 통과하는 코드를 추가하는 단계를 반복하여 구현한다.

### TDD Cycle&#x20;

* Red - 실패하는 테스트 코드를 작성, 인터페이스와 스펙에 집중한다.
* Green - 재빨리 테스트를 통과 시킨다. 올바른 방법이 아니어도 괜찮다.
* Blue(Refactor) - 리팩터링을 통해 코드를 올바르게 만든다. TDD에서 가장 중요한 부분이지만, 간과될 때가 많다.

### TDD 개발 방식

* &#x20;일반적인 개발 방식과 TDD와 큰 차이점은 테스트 코드를 작성한 뒤에 실제 코드를 작성하는 것이다.

### TDD 개발 방식의 장점&#x20;

* 보다 튼튼한 객체 지향적인 코드 생산이 가능하다
* 재설계 시간의 단축된다.
* 자동화 된 유닛 테스팅을 전제로 특정 버그를 빠른 시간내에 찾을 수 있어 디버깅 시간의 단축된다.
* 테스팅을 자동화 시킴으로 보다 정확한 테스트 근거를 산출이 가능하여 테스트 문서의 대체가 가능하다.&#x20;
* 추가 구현의 용이하다.

### TDD 개발 방식의 단점

*   TDD 방식의 개발 시간은 일반적인 개발 방식에 비해 시간이 투자되기 때문에 생산성이 저하된다&#x20;

    &#x20;

## Jest

### Jest란?

* 페이스북에서 만든 테스팅 라이브러리로 React와 더불어 자바스크립트에서도 좋은 반응을 얻고있다.
* Jest 이전에는 기존 자바스크립트 테스팅 라이브러리를 조합해서 사용하였는데 여러개를 사용하면서 서로 겹치는 기능들이 존재하여 개발자들에게 혼란을 주었다. 하지만 Jest 라이브러리를 사용하면 다른 테스팅 프레임워크들을 제공하여 상당히 편리하게 사용이 가능하다.&#x20;

### Jest 사용 예제

테스트 케이스를 정의할 때 크게 두 가지 방법으로 사용한다.

1. test 함수로 개별 테스트를 나열하는 방식
2. BDD 스타일로 주체- 행위 중심으로 테스트를 조직화 하는 방식

test 함수로 개별 테스트 써보자

```typescript
test('add', () => {
	expect(add(1, 2)).toBe(3);
});
```

BDD 스타일로 테스트 대상과 행위를 명확히 드러내자

```typescript
describe('add', () => {
	it('returns sum of two numbers', () => {
		expect(add(1, 2)).toBe(3);
	});
});


```

다양한 경우를 고려한 방법

```typescript
const context = describe;

describe('add', () => {
	context('with no argument', () => {
		it('returns zero', () => {
			expect(add()).toBe(0);
		});
	});

	context('with only one number', () => {
		it('returns the same number', () => {
			expect(add(1)).toBe(1);
		});
	});

	context('with two numbers', () => {
		it('returns sum of two numbers', () => {
			expect(add(1, 2)).toBe(3);
		});
	});

	context('with three numbers', () => {
		it('returns sum of three numbers', () => {
			expect(add(1, 2, 3)).toBe(6);
		});
	});
});
```

## Describe - Context - It 패턴

### Describe - Context - It 패턴이란?

* BDD 테스트 코드 작성 패턴으로 코드의 행동을 설명하는 테스트 코드를 작성한다.
* 코드의 행동을 섬세하게 설명하는데 적합한 패턴이다.

### Describe - Context - It 패턴 사용하는 이유

* 테스트 코드를 계층 구조로 만들어준다.&#x20;
* 테스트 코드를 추가하거나 읽을 때 필요한 경우 큰 도움이된다.

| 키워드               | 설명                   |
| ----------------- | -------------------- |
| <h3>Describe</h3> | 설명할 테스트 대상을 명시한다.    |
| <h3>Context</h3>  | 테스트 대상이 놓인 상황을 설명한다. |
| <h3>It</h3>       | 테스트 대상이 행동을 설명한다.    |

{% hint style="info" %}
**`Context`**`문 작성시 with 또는 when으로 시작하도록한다`

**`It`**구문은 It returns treu, It response 404등과 같이 심플하게 설명 할수록 좋다.
{% endhint %}

사용 예제

```typescript
describe("add", () => {// add 함수는 
  context("with no argument", () => {// 인자가 없을 경우
    it("returns zero", () => { // 0값을 리턴한다
      expect(add()).toBe(0);
    });
  });
  context("with only one arguments", () => {// 인자가 1개일 경우
    it("returns the same number", () => {// 2개의 숫자를 합해서 리턴한다.
      expect(add(2)).toBe(2);
    });
  });

  context("with only two arguments", () => {// 인자가 2개일 경우
    it("return sum of two numbers", () => {// 2개의 숫자를 합해서 리턴한다.
      expect(add(1, 2)).toBe(3);
    });
  });

  context("with only three arguments", () => {// 인자가 3개일 경우
    it("return sum of three numbers", () => {// 3개의 숫자를 합해서 리턴한다.
      expect(add(1, 2, 3)).toBe(6);
    });
  });
});

```

## 단위 테스트란?

* 단위 테스트는 우리가 작성한 코드가 의도한 대로 잘 작동하는지 검증하기 위한 절차이다.
* 함수와 메소드에 대한 테스트 케이스를 작성하는 절차를 말한다.

### 단위 테스트의 특징

* 단위 테스트는 매우 간단하고 명확하며 빠르게 실행되는 특징이 있다.
* 하나의 함수에 1개이상의 테스트가 존재할수 있고, 각각의 조건에 대한 유효성을 검증한다. 이렇게 작성된 단위 테스트가 많을수록 해당 로직에 대한 신뢰도가 높아진다.&#x20;
* 작게 쪼개진 단위테스트는 해당 로직이 어떤 역할을 하는지 쉽게 파악이 가능하다&#x20;

&#x20;

{% hint style="info" %}
&#x20;⚠️ TDD 에 대해서 주의할 점 테스트 코드를 작성한다고 해서 TDD 가 아닙니다. TDD Cycle 에 따라 테스트 코드를 먼저 작성하고, 구현하고, 리팩터링 하는 과정을 엄격하게 지켜서 개발을 진행해야 TDD 라고 할 수 있습니다. TDD 는 테스트 코드를 작성하는 것과 별개로 따로 연습이 필요하고 습관을 들여야하는 분야 입니다. 그리고 TDD 를 잘 하기 위해서는 테스트 코드 작성법 자체부터 공부를 하셔야 합니다. 당장은 TDD 보다 테스트 코드 작성에 익숙해지고 어떻게 하면 테스트 코드를 잘 작성할 수 있을까에 초점을 맞춰 공부하시면 좋습니다.
{% endhint %}

