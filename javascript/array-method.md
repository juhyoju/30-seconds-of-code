## Array method 

개발자가 알아야 할 자바스크립트의 핵심 메소드

### Array.prototype.map()

array.protype.map은 기본 배열의 각 요소에 변화된 값으로의 새로운 배열을 생성한다.  
그 결과, 기존 배열과 동일한 길이의 새로운 배열과 제공된 함수에 기반하여 변형된 요소로 반환한다.

```js
const arr = [1, 2, 3];
const double = x => x * 2;
arr.map(double); // [2, 4, 6]
```


### Array.prototype.filter()
필터링 함수를 사용하여 해당 함수에 `true`를 리턴하는 요소만으로 새로운 배열을 생성한다.  
그 결과, 기존 배열보다 작거나 같은 길이의 배열이 생성되며, 기존 배열의 요소와 동일한 요소를 포함한다.

```js
const arr = [1, 2, 3];
const isOdd = x => x % 2 === 1;
arr.filter(isOdd); // [1, 3]
```

### Array.prototype.reduce()
리듀서 함수와 초기값에 따라 모든 유형의 출력값을 생성한다.  
그 결과, 제공된 리듀서 함수에 기반한 정수, 객체, 배열을 사용할 수 있다.

```js
const arr = [1, 2, 3];

const sum = (x, y) => x + y;
arr.reduce(sum, 0); // 6

const increment = (x, y) => [...x, x[x.length - 1] + y];
arr.reduce(increment, [0]); // [0, 1, 3, 6]
```

### Array.prototype.find()
주어진 판별 함수에서 `true`를 반환하는 첫번째 요소를 반환하며, 그런 요소가 없을 경우 `undefined`를 반환한다.  
그 결과, 기존 배열의 단일 요소가 생성된다.

```js
const arr = [1, 2, 3];
const isOdd = x => x % 2 === 1;
arr.find(isOdd); // 1
```