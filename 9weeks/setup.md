---
description: 설계
---

# 😝 Setup

## 용어 정리&#x20;

* Product : 상품
  * Summary : 상품에 대한 요약 정보
  * Detail : 상품에 대한 상세 정보
  * Image : 상품 이미지&#x20;
  * Option : 상품에 대한 상세 옵션 종류(색상, 크기 등)
    * OptionItem : 옵션에 대한 상세 옵션 값(옵션이 색상이라면 이건 Blue, Red 같은 걸 의미함)
* Category : 상품에 대한 분류&#x20;
* Cart : 장바구니
  * LineItem: 장바구니에 담긴 것(상품, 옵션, 수량 등을 동시에 다룸)
    * 여기서도 Option과 OptionItem을 사용한다.
    * 용어는 동일하지만 Product와 다른 구성을 갖기 때문에, 여기서는 Product와 Order라는 접두어를 활용한다.
    * 시스템을 분리할 수 있다면, 근본적으로 나누는걸 추천(상품 정보 확인/ 장바구니/ 주문)
* Order : 주문
  *    여기서도 동일한 LineItem 활용
* User : 사용자

## 기능

* 상품 목록 확인
* 상품 상세 정보 확인
* 장바구니에 상품 담기
* 주문하기 -> 배송지 입력, 결제
* 주문 목록 확인
* 주문 상세 확인
* 로그인
* 회원 가입

## 화면

* 홈페이지 - <mark style="color:orange;">`/`</mark>
* 상품 목록 페이지 - <mark style="color:orange;">`/prodcuts`</mark>
* 상품 상세 페이지 - <mark style="color:orange;">`/products/{id}`</mark>
* 장바구니 페이지  - <mark style="color:orange;">`/cart`</mark>
* 주문 페이지 - <mark style="color:orange;">`/order`</mark>
* 주문 완료 페이지 - <mark style="color:orange;">`/order/complete`</mark>
* 주문 목록 페이지 - <mark style="color:orange;">`/orders`</mark>
* 주문 상세 페이지 - <mark style="color:orange;">`/orders/{id}`</mark>
* 로그인 페이지 - <mark style="color:orange;">`/login`</mark>
* 회원 가입 페이지 - <mark style="color:orange;">`/signup`</mark>
* 회원 가입 완료 페이지 - <mark style="color:orange;">`/signup/complete`</mark>

## 개발 환경 세팅

### REST API

> [REST API](https://docs.google.com/document/d/1bGYl3IDoX53cNBbZHNlsRhPLZQ3Qiu-Jm3gpqyu\_xI0/view)

### 개발 환경 세팅

* [기본 세팅](https://github.com/ahastudio/til/blob/main/react/20230205-setup-react-project.md)
* [CodeceptJS 세팅](https://github.com/ahastudio/CodingLife/tree/main/20211012/react#codeceptjs-%EC%82%AC%EC%9A%A9)

#### 추가로 설치할 라이브러리

1. [React Router](https://github.com/remix-run/react-router)
2. [styled-components](https://github.com/styled-components/styled-components)
3. [styled-reset](https://github.com/zacanger/styled-reset)
4. [usehooks-ts](https://github.com/juliencrn/usehooks-ts)
5. [Axios](https://github.com/axios/axios): REST API 사용을 위한 HTTP 클라이언트.
6. [tsyringe](https://github.com/microsoft/tsyringe)
7. [reflect-metadata](https://github.com/rbuckton/reflect-metadata)
8. [usestore-ts](https://github.com/seed2whale/usestore-ts)
9. [jest-dom](https://github.com/testing-library/jest-dom): React Testing Library에서 활용할 수 있는 DOM 확인용 Matcher 모음.
10. [MSW](https://github.com/mswjs/msw)

