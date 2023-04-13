# 😑 TSyringe

### 학습 키워드

## TSyringe

* Prop Driling의 문제를 해결 하기위한 방법 중 하나인 TypeScript용 의존성 주입 라이브러리이다.
* `TSyringe`는 TypeScript의 Decorator를 사용하여 **의존성 주입**을 설정하며, 클래스와 함수 등의 의존성을 관리할 수 있습니다. 이를 통해 코드의 가독성과 유지보수성을 높일 수 있습니다.
* reflect-metadata와 같이 사용이 가능하다.
* `TS`yringe는 다양한 주입 방식 기능을 제공한다.
  * 생성자 주입(Constructor Injection), 프로퍼티 주입(Property Injection), 메서드 주입(Method Injection)등이 있다.

#### 설치 및 사용 방법

```sh
npm i tsyringe reflect-metadata
```

## 의존성 주입(Dependency Injection)

객체가 다른 객체에 의존할 때 해당되는 객체를 직접 생성해서 사용한다. 이러한 방식은 **유연성과 확장성을 저하**시킨다. 이러한 문제점 때문 **의존성 주입**을 사용하는데 **의존성 주입**이란 **객체지향 프로그래밍에서 사용 되는 디자인 패턴이며 객체와 객체간의 결합도를 낮추기 위해 많이 사용**된다.&#x20;

* 의존성 주입은 다양한 방식으로 구현이 가능하며 이러한 방식들은 코드 가독성과 유지보수에 용이하다.

## reflect-metadata

* TypeScript와 JavaScript에서 사용되는 라이브러리이다.&#x20;
* 메타데이터는 코드 자체의 정보를 의미한다.
* TypeScript에서 데코레이터를 사용할 때 유용하며 데코레이터는 클래스나 메소드에 메타데이터를 추가하는 기능을 제공한다.

{% hint style="info" %}
`import "reflect-metadata"` 임포트시 최상위 부모 컴포넌트 맨위에 선언해서 사용한다.
{% endhint %}

sington (싱글톤)
