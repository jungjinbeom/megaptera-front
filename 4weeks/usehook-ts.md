# 😚 usehook-ts

## usehooks-ts

React와 TypeScript를 함께 사용할 때 유용한 Custom Hook 라이브리러이다.

* **useBoolean :** boolean 값을 다루는 CustomHook
* **useEffectOnce :** 컴포넌트가 마운트 될 때 한번만 실행되는 useEffect CustomHook
* **useFetch :** 외부 API와의 통신을 관리하는 Hook입니다.
* **useInterval :** 일정 시간마다 함수를 실행하는 Hook입니다.
* **useEventListener :** 이벤트를 등록하고, 등록한 이벤트를 제거할 때 사용합니다.
* **useLocalStorage :** Local Storage에 값을 저장하고, 가져오는 Hook입니다.
* **useDarkMode :** 다크 모드를 사용하는 애플리케이션에서 사용자의 시스템 환경 설정에 따라 라이트 모드 또는 다크 모드를 적용하는 컴포넌트를 만들기 위해 사용되는 Custom Hook입니다.

## SWR

SWR은 Next.js에서 만든 데이터 패칭 라이브러리이다.

* 캐시된 데이터를 사용하여 화면을 렌더링하고 동시에 새로운 데이터를 가져와서 캐시를 업데이트 한다&#x20;
* fetching에 필요한 모든 것을 제공하며, SSR 및 CSR 모두에서 작동한다.
* 기본적으로 캐시를 사용하므로, 데이터를 가져올 때마다 네트워크 요청을 보내지 않아도 되므로, 성능향상에 도움이된다

## React-query

React-query 서버 상태 관리 라이브러리이다.

* API와의 통신을 단순화하고 캐싱, 리트라이, 인터벌 쿼리등의 기능들을 사용할 수 있다&#x20;
* 데이터 캐싱 및 무효화: `react-query`는 요청한 데이터를 자동으로 캐싱하고, 해당 데이터가 무효화되는 경우 다시 요청합니다.
* 옵티미스틱 업데이트: API 요청이 성공한 후에 UI를 업데이트하는 것이 아니라, 요청을 보내는 즉시 UI를 업데이트합니다.
* 리트라이: 요청이 실패한 경우, `react-query`는 요청을 자동으로 다시 시도합니다.
* 인터벌 쿼리: 지정된 시간마다 데이터를 다시 가져오도록 구성할 수 있습니다.
* SSR 지원: `react-query`는 서버 사이드 렌더링(SSR)을 지원합니다.

\
