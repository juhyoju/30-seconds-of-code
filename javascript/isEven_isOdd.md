## isEven

지정된 숫자가 `짝수`인지 판별한다.

1.  연산자 `%`를 이용하여 숫자가 홀수인지 짝수인지 확인한다. (% 연산자: 나머지를 반환)
2.  짝수이면 `true`를 반환하고 홀수이면 `false`를 반환한다.

```js
const isEven = (num) => num % 2 === 0;

/* Example */
isEven(3); // false
```

<br>

## isOdd

지정된 숫자가 `홀수`인지 판별한다.

1.  연산자 `%`를 이용하여 숫자가 홀수인지 짝수인지 확인한다. (% 연산자: 나머지를 반환)
2.  홀수이면 `true`를 반환하고 짝수이면 `false`를 반환한다.

```js
const isOdd = (num) => num % 2 === 1;

/* Example */
isOdd(3); // true
```
