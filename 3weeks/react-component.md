# 😑 React Component

## Thinking in React

* step 1: Break the UI into a component hierarchy
  * 컴포넌트 계층 구조 나누기
* step 2: Build a static version in React
  * 리액트 정적 버전 빌드

## REST API와 GraphQL

### REST API란?

* REST(Respresentational State Transfer)의 약자로 자원을 이름으로 구분하여 자원의 상태를 주고 받는 것을 의미한다.
* HTTP 메소드인 GET, POST, PUT/PATCH, DELETE 을 사용해 서버에 수행해야 할 동작을 지정하고 요청하는 방법&#x20;
* resource 중심
  * REST API 주요한 정보를 resource 라고 한다.
  * 문서, 이미지, 일반적 객체값 등을 포함 한다.
  * 클라이언트는 URI를 이용해서 자원을 지정하고 해당 자원의 상태에 대한 조작을 Server에 요청한다.

### GraphQL란 ?&#x20;

* 페이스 북에서 만든 쿼리언어 입니다.
* Graph 자료 구조
* Query(Read)에서 얻고자 하는 걸 지정한다.
  * 읽기 전용으로 데이터를 가져오기 위한 메서드
* Mutation(Command: Create, Update, Delete), Subscription(Event)
  * Mutation은 데이터를 변경한 후 가져오기 위한 메서드&#x20;
  * Subscription은 실시간으로 변경된 데이터를 가져오기 위한 요청 방식이다.
  * Subscription은 웹소켓을 통해 소켓 통신을 열어두고 데이터 업데이트를 알리는 방식이다

## JSON

### JSON란?

* 클라이언트와 서버 간의 HTTP 통신을 위한 데이터 포맷
* key-value 쌍으로 이루어진 데이터 오브젝트이다
* 자바스크립트와의 호환성이 좋다.
* JSON은 텍스트 형식으로 이루어져 있으며, 데이터 객체와 배열을 표현하는 데 사용

### JSON의 이점은?

* 가독성이 뛰어나다.
* 데이터 전송 및 교환이 쉽다.
* 다양한 프로그래밍 언어에서 지원한다.



## React Component

### Component 란 ?&#x20;

> 리액트로 만들어진 앱을 이루는 최소한의 단위&#x20;

### React의 강력한 특징 둘 중 하나

* **Component-Based**
  * Component 기반으로 개발을 한다.
  * 간단한 Component 하나하나로 복잡한 UI 구현한다.

### Component를 나누는 기준

* **SRP(단일 책임 원칙)**
  * 컴포넌트가 너무 커지고 있다면&#x20;
* **CSS**
  * 이미 알고 있는 기준을 재활용
* **Design’s Layer (디자인 측면**)
  * 레이어도 트리 형태로 이루어짐
* I**nformation Architecture (JSON Schema의 영향)**
  * 실제로 엄청 많이 쓰게 됨. 자연스러운 SRP를 위해서 사실상 강제됨.

## Props&#x20;

### Props란?

> Properties의 줄임말로 상위 컴포넌트에서 하위 컴포넌트로 값을 전달해주는 방식이다

* 상위 컴포넌트에서 넘겨준 props값이 변할 시  값을 받는 하위 컴포넌트는 리렌더링 된다.
* 값에 이름을 붙여서 전달한다.&#x20;
* 나누어진 컴포넌트를 서로 연결하는 방법
* TypeScript를 잘 사용 하거나 못 사용하는 포인트 중 하나
  * 적절한 균형점 잡는 게 중요하다.
* 테스트 코드를 작성하면 재사용성을 평가하기 쉬워진다.

{% hint style="info" %}
Props는 불변성을 가읽기전용 값이다.
{% endhint %}

## Extract Function(함수 추출)

### Extract Function란?

> Extract Function(함수 추출)은 함수를 정의할 때 각 기능들이 어느정도 코드가 길고 읽기가 어렵다면 그 기능을 함수로 추출하는 방법입니다.
>
> SRP를 위한 수단, 변화와 크기(영향 범위)를 제약한다.

* 길게 코드를 작성하고, 적절히 자를 수 있는 부분이 보일 때 **함수로 추출**
* 코드를 작성하기 어려운 상황에 직면했을 때 **함수로 추출**

{% hint style="info" %}
컴포넌트 나누는 기준이 애매하면 다시 하나의 컴포넌트로 합쳤다가(Inline Method) 다시 나눠줘도 된다.
{% endhint %}

> 리팩토링에서 사용하는 기[ract Function](https://refactoring.com/catalog/extractFunction.html)
>
> [Inline Function](https://refactoring.com/catalog/inlineFunction.html)

### ****

### ****

## **키워드 정리**&#x20;

### 명령어 프로그래밍

* 프로그램의 상태와 상태를 변경시키는 구문의 관점에서 연산을 설명하는 프로그래밍 패러다임의 일종이다.
* 명령어 프로그래밍은 **어떻게 그것을 해결할 것인가**에 초점이 맞춰져 있다.

### 선언형 프로그래밍

* 프로그램이 무엇을 해야 할지를 나타낸 경우를 **선언형**이라고 한다.
* 웹페이지를 나타낼 때 **어떤 방법**으로 페이지를 나타내는 것이 아닌 **무엇을** 화면에 나타내야 할지에 초점이 맞춰져 있다.

### 명령형 선언형 예시&#x20;

> 낯선 사람이 당신에게 OO호텔이 어디 있는지를 묻는다. 당신은 그곳이 어디 있는지 잘 안다. 이때 당신은 이렇게 말한다.

* 명령형 방식 : "여기서 쭉 직진하시다가 롯데리아가 보이시면 우회전 하세요. 직진하다가 두 번째 신호등에서 좌회전하세요. OO호텔이 보일 겁니다"
* 선언형 방식 : "OO 호텔은 xxx동 xxx로 xx길 10에 있습니다.

명령형은 OO호텔에 어떻게 가는지에 대해서, 선언형은 어떤 곳을 가야하는 지를 말했다.

### **SRP**(단일 책임 원칙)&#x20;

* 객체는 단 하나의 책임만 가져야 한다는 원칙을 말한다.
* 함수나 클래스는 단 하나의 기능만 수행해야 한다.

### Atomic Design

* 우리가 잘 알고 있는 계층형 구조를 몇 가지 카테고리로 묶은 방법
* React를 이용하여 컴포넌트 개발할 때 사용하는 디자인 기법 중 하나로 효율적인 인터페이스 디자인 시스템을 만들어내기 위해 사용된다.
* ATOMS(원자) => MOLECULES(분자) => ORGANISMS(유기체) => TEMPLATES(템플릿) => PAGES(페이지)
* 디자인 부품을 만들어 조립한다.
