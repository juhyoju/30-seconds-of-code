## Can I use an arrow function as the callback for an event listener in JavaScript?

### Arrow Functions

자바스크립트 `ES6`은 함수를 정의하고 작성하는 새로운 방법인 `화살표 함수`를 도입했다.

> 화살표 함수에는 `this`에 대한 고유한 바인딩이 없으므로 `this`를 둘러 싸고 있는 어휘적 맥락의 `this`의 값을 보존한다.

<br>

### Event listener callbacks

브라우저 측 자바스크립트를 작성할 때 종종 수행하는 한 가지 작업은 `이벤트 수신기`를 생성하는 것이다.

```js
const toggleElements = document.querySelectorAll(".toggle");
toggleElements.forEach((el) => {
  el.addEventListener("click", function () {
    this.classList.toggle("active");
  });
});
```

- `NodeList.prototype.forEach()`를 사용하여 주어진 선택기와 일치하는 노드를 반복한다.
- `click` 이벤트에 대한 콜백으로 일반 함수를 사용하는 `EventTarget.addEventListener()`를 사용하여 클릭된 요소의 활성/비활성을 토글한다.
- 정규 함수를 사용하고 있기 때문에 콜백 내부의 `this` 컨텍스트는 이벤트가 발생한 요소에 바인딩된다.

<br>

### Arrow functions as callbacks

이미 설명했듯이 화살표 함수는 `this`에 대한 바인딩이 없다.  
이전 코드의 콜백을 화살표 함수로 전환하면 `this` 컨텍스트는 `글로벌 컨텍스트`를 의미하는데 이 경우에는 `window` 객체이다.

```js
const toggleElements = document.querySelectorAll(".toggle");
toggleElements.forEach((el) => {
  el.addEventListener("click", () => {
    this.classList.toggle("active"); // `this` refers to `window`
    // Error: Cannot read property 'toggle' of undefined
  });
});
```

이 코드는 `classList` 속성이 없는 `window` 객체로 인해 이벤트 수신기를 종료하고 콜백을 실행하는 matching 요소를 클릭할 때마다 에러가 발생한다.  
이를 해결하기 위해 콜백 함수의 첫 번째 인수와 필요에 따라 `Event.target`와 `Event.currentTarget`을 사용하면 된다.

```js
const toggleElements = document.querySelectorAll(".toggle");
toggleElements.forEach((el) => {
  el.addEventListener("click", (e) => {
    e.currentTarget.classList.toggle("active"); // works correctly
  });
});
```
