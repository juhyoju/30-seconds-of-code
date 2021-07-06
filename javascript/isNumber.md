## isNumber

주어진 값이 정수인지 판별한다.

 ```javascript
const isNumber = val => typeof val === 'number' && val === val;
```

- 매개변수의 값이 정수이면 `true`를 반환
- 매개변수의 값이 정수가 아니거나, 값이 `NaN` 또는 `Infinity` 일 경우 `false` 반환

```js
isNumber(1); // true
isNumber('1'); // false
isNumber(NaN); // false
```