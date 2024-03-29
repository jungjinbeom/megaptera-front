# 👿 Routes

## 라우터란?

패킷을 목적까지 전달하기 위해 다음 네트워크 지점을 장치나 컴퓨터 내의 소프트웨어

* 인터넷을 작동시키는 네트워크 하드웨어 구성요소는 라우터 이다&#x20;
* 인터넷의 핵심은 IP 패킷들이 여러 개의 다른 라우터를 통해 정확히 목적지로 라우팅 되는 것이다.
  * 인터넷은 라우터의 기능 없이 존재 할 수가 없다.
* 라우터는 여러 개의 통신 회선에 연결된 특수한 컴퓨터로 한 회선으로 부터 받은 패킷들을 조사하여 그 패킷의 최종 목적지에 가까운 회선으로 패킷을 라우팅 하도록 하는 프로그램이다.



## React Router

React 애플리케이션에서 클라이언트 측 라우팅을 지원하기 위한 라이브러리이다.

* 단일 페이지 애플리케이션(SPA)에서 브라우저 주소창에 입력한 URL 감지하고 해당 URL에 맞는 페이지로 이동한다.
* React Router를 사용하면 라우트의 매개변수와 쿼리 문자열을 쉽게 추출하여 사용할 수 있다.
* React Router는 여러가지 컴포넌트를 제공하며 이를 **조합하여 필요한 라우팅 로직을 구현**할 수 있다.
  * `Browser Router` : HTML5 HistoryAPI를 사용하여 클라이언트 측 라우팅을 제공하는 라우터이다
  * `Route` : URL이 일치하는 컴포넌트를 렌더링한다.
  * `Link` : 클릭할 수 있는 링크를 생성한다.
  * `NavLink` : 현재 URL과 일치하는 경우 활성화된 상태로 스타일을 적용하는 `Link` 컴포넌트이다.
  * `Switch` : 일치하는 `Route` 중에서 첫 번째 Route만 렌더링 한다.
  * `Memory Router` : 브라우저의 상태나 브라우저의 기록에 영향을 주지 않고 HTML5 History API 대신 메모리 내에서 URL 관리한다. URL 경로에 따라 컴포넌트를 렌더링 한다.
  * `Navigate` : 라우팅 경로를 변경하는 컴포넌트이다.
    * `history.push()`같은 메서드를 사용하지 않고 라우팅 경로 변경이 가능하다.
  * `useNavigate`: React Router 제공되는 Hook으로 라우팅 경로를 변경하는 함수를 반환해준다.
    * `const navigate = useNavigate()`을 선언해서 사용이 가능하다.
    * 위에 함수를 사용하여 경로 변경이 가능하다.
      * 사용 예시 `navigate("/path")`
