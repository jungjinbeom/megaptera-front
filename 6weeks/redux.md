# 😐 Redux 따라하기

### 학습 키워드

## Redux

JavaScript 언어를 위한 상태관리 라이브러리이다.

* 복잡한 애플리케이션 상태를 관리하기 쉽고 예측가능하게 설계되어있다.
* 상태를 단일 객체로 표현하고 액션을 통해 상태를 업데이트가 되며 업데이트 순차적으로 이루어져 상태 변경을 예측 가능한 방식으로 추적이 가능하다&#x20;

#### Redux의 주요 개념

* 상태(state) : 애플리케이션에서 사용되는 모든 데이터를 담고있는 객체
* 액션(Action) : 상태를 변경하기 위한 객체&#x20;
* 리듀서(Reducer) : 액션을 처리하고, 새로운 상태를 반환하는 순수 함수
* 스토어(Store) : 상태와 리듀서를 포함하여, 애플리케이션 상태를 유지한다

## Reflect

ECMAScript 2015에서 추가된 내장 객체이며 메타프로그래밍을 위한 메소드를 제공한다.

**`Reflect` 객체의 주요 메소드**

* `Reflect.apply(target, thisArg, argumentsList)`: 함수를 호출합니다.
* `Reflect.construct(target, argumentsList[, newTarget])`: 생성자 함수를 호출하여 객체를 생성합니다.
* `Reflect.defineProperty(target, propertyKey, attributes)`: 객체의 속성을 정의합니다.
* `Reflect.deleteProperty(target, propertyKey)`: 객체의 속성을 삭제합니다.
* `Reflect.get(target, propertyKey[, receiver])`: 객체의 속성 값을 반환합니다.
* `Reflect.has(target, propertyKey)`: 객체가 속성을 가지고 있는지 여부를 반환합니다.
* `Reflect.set(target, propertyKey, value[, receiver])`: 객체의 속성 값을 설정합니다.

&#x20;
