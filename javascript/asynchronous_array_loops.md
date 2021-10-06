## Asynchronous array loops in JavaScript

비동기식 운영은 많은 개발자들을 곤경에 빠뜨리는 것 같다. 이는 특히 어레이에 대한 루핑과 결합될 때 그렇습니다.
각 옵션을 사용할 수 있는 몇 가지 주의사항이 있기 때문입니다.

 <br>

### 0. Synchronous loop(동기 루프)

기본적으로 사용하던 동기 루프

```js
for (var i=0; i < array.length; i++) {
  var item = array[i];
  // do something with item
```

for문보다 가독성 및 유지 관리 측면에서 더 나은 `forEach문`을 자주 사용하게 됨

```js
array.forEach((item) => {
  // do something with item
});
```

개발 진행 시 배열 안에서 item에 대한 비동기 처리가 필요한 경우가 발생할 때 버그가 발생할 수 있음  
**for, forEach에서는 모든 비동기 작업이 끝나는 것을 대기하지 않음**

<br>

## 따라서,

아래와 같은 방법으로 loop를 비동기화할 수 있다.

<br>

### 1. For loops

- 배열 요소에 대한 비동기 연산을 수행할 때 `async`와 `for`(또는 for...of) 루프를 결합하는 것이 가장 간단한 옵션일 수 있다.
- `for` 루프에서 `await`를 사용하면 코드가 중지되고 비동기 작업이 완료될 때까지 기다린 후 계속된다. 이는 순차적으로 실행된다는 것을 의미한다.

```js
const asyncUppercase = (item) =>
  new Promise((resolve) =>
    setTimeout(
      () => resolve(item.toUpperCase()),
      Math.floor(Math.random() * 1000)
    )
  );

const uppercaseItems = async () => {
  const items = ["a", "b", "c"];
  for (item of items) {
    const uppercaseItem = await asyncUppercase(item);
    console.log(uppercaseItem);
  }

  console.log("Items processed");
};

uppercaseItems(); // logs: 'A', 'B', 'C', 'Items processed'
```

<br>

### 2. Promises.all

- `Promise.all()`은 배열을 통한 비동기 루프에 대한 다른 옵션을 제공한다.
- 이전과 가장 큰 차이점은 `Promise.all()`은 모든 비동기 연산을 `병렬로 실행`한다는 것이다. 이는 promise가 제대로 이뤄지지 않는다는 것을 의미하며, 경우에 따라서는 문제가 될 수도 있다.
- 일반적으로 순차적으로 실행하겠다는 propmise을 원하는 경우가 드물기 때문에 이 솔루션이 가장 선호하는 솔루션이다.

```js
const asyncUppercase = (item) =>
  new Promise((resolve) =>
    setTimeout(
      () => resolve(item.toUpperCase()),
      Math.floor(Math.random() * 1000)
    )
  );

const uppercaseItems = () => {
  const items = ["a", "b", "c"];
  return Promise.all(
    items.map(async (item) => {
      const uppercaseItem = await asyncUppercase(item);
      console.log(uppercaseItem);
    })
  ).then(() => {
    console.log("Items processed");
  });
};
// logs: 'A', 'C', 'B', 'Items processed'
```

<br>

### 3. Array methods

- `Array.prototype.forEach()`과 같은 배열 메서드가 있다. `async/awit`와 잘 작동하지 않는다.
- 실행 가능한 유일한 해결책은 앞의 예제처럼 `Promise.all()`을 사용하는 것입니다.
- `async` 콜백을 `Array.prototype.forEach()`과 함께 사용하면 나머지 코드가 실행되고 비동기식 연산이 중단된다.

```js
const asyncUppercase = (item) =>
  new Promise((resolve) =>
    setTimeout(
      () => resolve(item.toUpperCase()),
      Math.floor(Math.random() * 1000)
    )
  );

const uppercaseItems = async () => {
  const items = ["a", "b", "c"];
  await items.forEach(async (item) => {
    const uppercaseItem = await asyncUppercase(item);
    console.log(uppercaseItem);
  });

  console.log("Items processed");
};

uppercaseItems(); // logs: ''Items processed', 'B', 'A', 'C'
```
