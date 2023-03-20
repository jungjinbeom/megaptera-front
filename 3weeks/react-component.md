# 😑 React Component

### 데이터

Back-End에서 JSON 형태로 데이터를 돌려주는 API를 제공한다고 가정&#x20;

### REST API

* REST(Respresentational State Transfer)의 약자로 자원을 이름으로 구분하여 자원의 상태를 주고 받는 것을 의미한다.
* HTTP 메소드인 GET, POST, PUT/PATCH, DELETE 을 사용해 서버에 수행해야 할 동작을 지정하고 요청하는 방법&#x20;
* resource 중심
  * REST API 주요한 정보를 resource 라고 한다.
  * 문서, 이미지, 일반적 객체값 등을 포함 한다.
  * 클라이언트는 URI를 이용해서 자원을 지정하고 해당 자원의 상태에 대한 조작을 Server에 요청한다.

### GraphQL

* 페이스 북에서 만든 쿼리언어 입니다.
* Graph 자료 구조
* Query(Read)에서 얻고자 하는 걸 지정한다.
  * 읽기 전용으로 데이터를 가져오기 위한 메서드
* Mutation(Command: Create, Update, Delete), Subscription(Event)
  * Mutation은 데이터를 변경한 후 가져오기 위한 메서드&#x20;
  * Subscription은 실시간으로 변경된 데이터를 가져오기 위한 요청 방식이다.
  * Subscription은 웹소켓을 통해 소켓 통신을 열어두고 데이터 업데이트를 알리는 방식이다

### JSON

* 개방형 표준 포맷으로 키-값쌍으로 이루어진 데이터 오브젝트이다
* 클라이언트와 서버의 데이터 교환 형식이다.
* [JSON 개요](https://www.json.org/json-ko.html)
* [JSON으로 작업하기](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Objects/JSON)
* [명령형 프로그래밍](https://ko.wikipedia.org/wiki/%EB%AA%85%EB%A0%B9%ED%98%95\_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [선언형 프로그래밍](https://ko.wikipedia.org/wiki/%EC%84%A0%EC%96%B8%ED%98%95\_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)

### 컴포넌트 계층 구조

#### React의 강력한 특징 둘 중 하나&#x20;

* **Component-Based**
  * Component 기반으로 개발을 한다.
  * 간단한 Component 하나하나로 복잡한 UI 구현한다.
  * **Component를 나누는 기준**
    * **SRP**(Single Responsibility Principle)&#x20;
      * 단일 책임 원칙
    * 하나의 Component가 너무 커지면  Component 단위로 나눠준다&#x20;
    * 디자인 레이어 기준으로 나눠준다.
    * Information Architecture(JSON Schema의 영향)&#x20;
      * Back-End에서 내려준 JSON의 데이터의 구조로 컴포넌트 생성하는데 제약이 걸릴수도 있다.&#x20;
      * 이런 경우 Front-End에서 데이터를 한번 더 가공하거나 Back-End에게 데이터 구조 변경을 요청한다.

### Atomic Design

* 우리가 잘 알고 있는 계층형 구조를 몇 가지 카테고리로 묶은 방법
* React를 이용하여 컴포넌트 개발할 때 사용하는 디자인 기법 중 하나로 효율적인 인터페이스 디자인 시스템을 만들어내기 위해 사용된다.
* ATOMS(원자) => MOLECULES(분자) => ORGANISMS(유기체) => TEMPLATES(템플릿) => PAGES(페이지)
* 디자인 부품을 만들어 조립한다.
