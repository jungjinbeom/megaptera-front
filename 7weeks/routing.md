# 😔 Routing

## HTML DOM(Document Object Model) API

HTML 문서를 표현하는 객체 모델이며 JavaScript를 통해 HTML문서를 동적으로 제어 할 수 있는 API이다.

* HTML 문서는 트리 구조로 구성되어 있으며 이러한 구조를 기반으로 각 요소(element)를 객체로 표현한다.
* HTML 요소의 속성(attribute)이나 내용(content)을 변경하거나, 이벤트(event)를 처리하고, 새로운 요소를 동적으로 생성하거나 삭제할 수 있습니다.
* **DOM API**는 웹 브라우저에서 기본적으로 지원되는 API이며, JavaScript를 사용하여 **DOM API**를 조작할 수 있다. &#x20;
* **DOM API는** 다양한 메서드와 속성을 제공하고 있으며 사용하면 웹페이지의 동적인 변경이 가능해지고 사용자 친화적이고 효율적인 웹페이지가 제공이 가능하다.
* 예시로 **DOM API에** HTML 요소 를 생성 시킬 수 있는 `document.createElement()`  메서드를 사용할 수 있는데 메서드를 사용하여 객체를 생성하여 객체의 속성(attribute)이나 이벤트(event) 처리가 가능한 객체를 생성할 수 있다. &#x20;

## location

**DOM API**에서 제공하는 객체 중 하나로 웹페이지의 URL의 정보를 가지고 있다.

* `window.location`을 통해 접근이 가능하며 이를 통해 현재 웹페이지의 URL 정보를 얻거나, 새로운 URL이동이 가능하다.
* `location`은 다양한 메서드와 프로퍼티를 제공한다.
  * `location.href` : 값을 변경하면 새로운 URL로 이동할 수 있다.
  * `location.protocol` : 현재 웹 페이지의 프로토콜(http,https 등)정보를 반환한다.
  * `location.hostname` : 현재 웹 페이지의 호스트 이름을 반환한다.
  * `location.port` : 현재 웹 페이지의 포트번호 정보를 반환한다.
  * `location.pathname` : 현재 웹 페이지의 경로 정보를 반환한다.
  * `location.search` : 현재 웹 페이지의 쿼리스트링 정보를 반환한다.
  * `locaiton.hash` : 현재 웹 페이지의 해시 정보를 반환한다.
  * `location.assign()` : 새로운 URL로 이동한다.
  * `location.reload()` : 현재 페이지를 새로고침 한다.
  * `location.replace()` : 현재 페이지를 새로운 URL 변경해준다.
