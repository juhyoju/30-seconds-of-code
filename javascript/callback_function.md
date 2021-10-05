## What is a callback function?

- 콜백 함수는 다른 함수에 인수로 전달된 함수로 외부 함수 내부에서 호출되어 일종의 루틴이나 작업을 완료한다.
- 콜백 함수는 이벤트가 발생하거나 작업이 완료되면 실행되는 경우가 많다.

### Synchronous callbacks (동기식 콜백)

동기식 콜백은 `즉시, 순차적으로` 실행되는 콜백 함수이다.  
`Array.protype.map()`의 첫번째 인수로 전달된 함수는 동기 콜백의 좋은 예시이다.

```js
const nums = [1, 2, 3];
const printDoublePlusOne = (n) => console.log(2 * n + 1);

nums.map(doublePlusOne); // logs: 3, 5, 7
```

- 요청과 결과가 동시에 일어남
- 요청 처리 속도에 따라 응답을 바로 받거나 대기 시간이 발생할 수 있음
- 프로그램은 응답이 완료될 때까지 정지되고 응답을 받고 나서야 진행함

### Asynchronous callbacks (비동기식 콜백)

비동기식 콜백은 `비동기 작업이 완료된 후` 코드를 실행하는 콜백 함수이다.  
`Promise.protype.then()` 내에서 실행되는 함수는 다음과 같은 비동기식 콜백의 좋은 예시이다.

```js
const nums = fetch('https://api.nums.org'); // Suppose the response is [1, 2, 3]
const printDoublePlusOne = (n) => console.log(2 * n + 1);

nums.then(printDouble); // logs: 3, 5, 7
```

- 기능을 요청한 후 다른 작업을 하고 있다가 끝났다는 이벤트 받고 나면 이후의 처리를 하면 되기 때문에 속도가 빠름

```js
// #1
console.log('Hello');
// #2
setTimeout(function () {
  console.log('Bye');
}, 3000);
// #3
console.log('Hello Again');
```

`setTimeout()`은 Web API의 한 종류로, 코드를 바로 실행하지 않고 지정된 시간만큼 기다렸다가 로직을 실행한다. `비동기 방식`으로 실행되기 때문에 일단 실행하고 바로 다음 코드인 `console.log('Hello Again')`으로 넘어온다.

위 코드에 대한 실제 결과 값은

- `Hello` 출력
- `Hello Again` 출력
- 3초 있다가 `Bye` 출력
