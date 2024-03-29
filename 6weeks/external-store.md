# 🤥 External Store

### 학습 키워드

## 관심사의 분리(Soc)

**컴퓨터 프로그램을 구별된 부분으로 분리시키는 디자인 원칙**\
하나의 함수, 변수, 클래스, 컴포넌트에게 **한번에 다양한 기능을 부여하게 되면 그 코드를 읽는 사람은 혼란스러울 수 있다**. 이러한 해결방법은 **한번에 한 가지 기능에  동작하게 단위를 잘게 나누는 것**이다. 즉, **코드를 단위 별로 하나의 관심사만 갖도록 하고 그 관심사에 대해서만 충실히 동작하도록 만들어야 한다.**

**관심사 분리의 장점**

* 코드의 단위를 줄일수 있고 코드에 대한 파악이 빨라져서 문제를 빠르게 해결할 수 있다.
* 코드가 더욱 명료해지면서 코드의 역할이 잘 드러나게된다.
* 코드의 역할이 잘 분리되어 있어 재사용성이 올라간다.
* 코드가 단일화 되어 시스템 유지 보수가 쉬워진다.&#x20;
* 로직이 분리되어 있어 테스트가 더 간단해지고 그에 대한 테스트 코드 작성이 쉬워진다.

#### View와 Logic의 분리&#x20;

* 관심사의 분리를 프론트엔드도 적용이 가능하다.&#x20;
* Custom Hook을 사용하여 Logic을 독립적인 함수로 분리하여 관심사 분리가 가능하다&#x20;



## &#x20;Layered Architecture(계층화 아키텍쳐)

이름 그대로 여러 레이어를 분리하여 레이어 마다 역할을 정해놓은 구조이며 가장 흔하게 사용되는 아키텍처 스타일로 모놀리식 아키텍쳐 중 하나이다.

#### 레이어 구조&#x20;

* 각 레이어는 애플리케이션에서 프레젠테이션 로직, 비즈니스 로직등의 주어진 역할을 수행한다.
* 일반적으로 프레젠테이션, 비즈니스, 퍼시스턴스, 데이터베이스 4개의 레이어로 구성한다.

#### Layered Architecture의 장점

* 코드가 역할마다 분리되어 있어 유지보수가 편하다.
* 코드가 역할마다 분리되어 있어 테스트가 간단하다.
* 레이어 계층마다 관심사의 분리가 잘되어있다.

## Flux Architecture

Facebook에서 개발한 웹애플리케이션의 구조를 설계하는 아키텍쳐 중 하나이다. 기**존 MVC 패턴의 의존성과 복잡성 때문에 문제가 발생한다.** Facebook은 이러한 해결방법으로  **단방향 데이터의 흐름 택하였으며 데이터가 한 방향으로만 흐르게 하는 것으로 애플리케이션의 복잡성을 낮추고 데이터 흐름을 예측 가능하도록 설계하였으며 이러한 구조를 FLUX 구조라고 합니다.**

#### Flux 아키텍처 구조

Flux 아키텍처는 4가지의 요소로 구성됩니다.

* Dispatcher - 데이터의 모든 흐름을 관리합니다.
* Store - 애플리케이션의 데이터를 저장하고 데이터를 사용하고 있는 View에 데이터 변경될 때 마다 알려줍니다.&#x20;
* View - 사용자의 인터페이스를 말합니다.
* Action - Dispatcher에 전달할 데이터를 생성합니다.

관심사 분리가 잘되어있어 코드 재사용성과 유지보성에 용이하고 데이터는 단방향 흐름이여서 디버깅에 용이하다.\
주로 React와 함께 사용되는 경우가 많으며 Flux Architecture를 이용하여 데이터를 효율적으로 관리 할 수 있다.\


## useReducer

React 내장 Hook 중 하나로 상태관리를 할수있는 Hook 이다.

* useState를 사용할 때보다 상태 구조가 더 복잡할 때 주로 사용된다.
* `state`, `dispatch` 두개의 값을 반환해준다.
  * `state` - 현재 상태를 나타내는 변수이다.
  * `dispatch` - 상태를 변경하는 함수이다.
    * `dispatch` 함수를 호출하면, 해당 액션 객체를 `reducer` 함수에 전달하여 `state` 값을 업데이트 한다 .
* 여러 개의 액션에 대해 동시에 상태 업데이트가 가능하며 상태 업데이트 로직을 한곳에 모아 관리가 가능하다.

## useCallback

React 내장 Hook 중 하나로 성능최적화를 위해 사용하는 Hook이다

* 함수를 캐싱하여 불필요한 렌더링을 줄여 컴포넌트 성능을 향상시킨다
* useCallback 두개의 매개변수를 받는다&#x20;
  * 첫 번째 매개변수 : 콜백함수
  * 두 번째 매개변수 : 의존성 배열&#x20;
    * 함수가 props로 전달되는 경우
      * 부모 컴포넌트 렌더링 시 자식 컴포넌트는 함수를 새로 생성하는데 useCallback을 캐싱하여 자식 컴포넌트의 불필요한 렌더링을 방지할 수 있다.
    * 함수 내부에서 참조하는 변수가 있는 경우&#x20;
      * 함수 내부에서 참조하는 변수가 변경될때마다 함수도 새로 성생 되는데 useCallback을 사용하면 변수가 변경될때마다 함수를 생성하게 설정이 가능하고 불필요한 함수 생성을 방지할 수 있다.

## sington (싱글톤)

GoF(Gang of Four)의 디자인 패턴 중 하나로, 클래스의 인스턴스를 하나만 생성하도록 보장하는 패턴

#### Singleton 패턴이 사용되는 상황

* 어떤 클래스의 인스턴스를 오직 하나만 생성하고, 이를 전역에서 사용해야 하는 경우
* 인스턴스 생성 비용이 매우 크거나, 시스템 자원을 많이 사용하는 경우
* 인스턴스를 생성할 때의 초기화 과정이 복잡하거나, 여러 곳에서 중복되어 수행되는 경우

#### 특징

* 클래스 내부에서 인스턴스를 생성하고, 외부에서는 이를 얻어올 수 있는 getter 메서드를 제공
* 인스턴스 생성과 관련된 메서드는 private으로 선언하여, 외부에서는 인스턴스를 생성할 수 없도록 함
* 인스턴스는 static으로 선언하여, 클래스의 모든 인스턴스에서 공유됨
* Singleton 패턴에서는 인스턴스가 하나뿐임을 보장하기 위해, 인스턴스 생성에 대한 동기화 처리를 해주어야 함

#### 장점

* 전역 변수를 사용하지 않고, 인스턴스를 공유하는 방식으로 구현되기 때문에, 전역 변수를 사용할 때 발생하는 문제점을 해결할 수 있다.
* 인스턴스 생성과 관련된 로직을 캡슐화하여, 유지보수성과 확장성을 높일 수 있다.
