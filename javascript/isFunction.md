## isFunction

인자가 함수인지 판별한다.

 ```javascript
const isFunction = val => typeof val === 'function';
```

- 매개변수의 값이 함수이면 `true`를 반환
- 매개변수의 값이 함수가 아니면 `false`를 반환

```js
isFunction('x'); // false
isFunction(x => x); // true
```
