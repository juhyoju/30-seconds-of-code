## isString

인자가 문자열인지 판별한다.

```js
const isString = val => typeof val === 'string';
```

- 매개변수의 값이 문자열이면 `true`를 반환
- 매개변수의 값이 문자열가 아니면 `false`를 반환

```js
isString('10'); // true
isstring("string"); // true

isstring(text);     // false
```