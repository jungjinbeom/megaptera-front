# 👺 Router

## RouterProvider

React-Router v6에서 부터 도입되었으며 React 컴포넌트 트리에서 라우터 인스턴스를 전역적으로 공유하는데 사용된다.

* 기존에 `BrowserRouter`과 같은 라우터 컴포넌트를 사용하여 각 페이지의 라우터 경로를 컴포넌트로 관리해왔으며 이 방식은 라우터를 여러 컴포넌트에서 공유하기 어렵다는 단점이 있다.
* `RouterProvider`를 사용하면 **라우터 인스턴스를 전역 컨텍스트에서 제공할 수 있으며**\
  **어떤 컴포넌트에서든 라우터 인스턴스를 가져와서 사용이 가능**하다. 이는 라우터를 좀 더 유연하게 제어 할 수 있게 된다.
* `createBrowserRouter`를 사용하여 라우터를 Object화 시켜 관리가 가능해졌다.
* &#x20;`RouterProvider`는 `Router` 컴포넌트와 함께 사용되며 `Router`는 `BrowserRouter`, `MemoryRouter`등과 같은 라우터 컴포넌트 중 하나와 사용할 수 있다.
