# 🧐 Virtual DOM

## Virtual DOM이란?

* 하나의 가상 메모리라고 생각하면 된다.
* 렌더링 이전의 화면이 내용을 담고있는 첫번째 가상돔과 업데이트 이후에 발생하는 두번째 가상돔을 비교해 Element가 어떻게 변했는지 비교 한 다음 차이가 있는 부분만을 실제 DOM에 적용한다.

### Virtual DOM을 쓰는 이유?

* 기존에 10개의 변경사항이 있는데 DOM 즉시 반영하면 10번의 렌더 과정이 일어나서 비효율적이다. 하지만 Virtual DOM은 변경사항이 있을 경우 바로 DOM에 반영하지 않고 변경 사항들을 모아뒀다가 한번에 DOM에 반영하기 때문에 상당히 효율적이다.

### Keyword

**diffing** : 리액트에서 부르는 용어로 첫번째 가상돔과 업데이트 이후에 발생하는 두번째 가상돔을 비교해 어떤 Element 변했는지 비교하는것

**선언형 API** : **무엇을** 나타내야하는지를 프로그래밍적으로 표현한 것

**선언형 API** **예시**

* **명령형 접근 방식(HOW):**\
  "OO님 디자인팀에서 디자인해준 페이지를 기반으로 페이지를 만든다음에, 데이터베이스에서 전체 유저 리스트에 대해, AWS ses를 통해 메일을 보내는 스크립트를 만들어 실행해주세요."

```javascript
<ul id=”list”></ul>

<script>
var arr = [1, 2, 3, 4, 5]
var elem = document.querySelector("#list");

for(var i = 0; i < arr.length; i ++) {
  var child = document.createElement("li");
  child.innerHTML = arr[i];
  elem.appendChild(child);
}
</script>

```

* **선언형 접근 방식(WHAT):**\
  "OO님 프로모션 메일 보내주세요."

```javascript
const [arr, setArr] = useState([1, 2, 3, 4, 5]);
return (
  <ul>
    {arr.map((elem) => (
      <li>{elem}</li>
    ))}
  </ul>
);
```

{% hint style="info" %}
**Virtual DOM의 함정**

Virtual DOM은 DOM을 거치기 전에 하나의 레이어를 더 거쳐가는 동작이기 때문에 직접DOM을 조작하는것보다 느리다.
{% endhint %}
