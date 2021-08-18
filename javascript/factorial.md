## factorial

팩토리얼(!) 계산법  
예) 3팩토리얼(!) = 3 _ 2 _ 1 = 6

<br>

- 재귀 사용
- `n =< 1` 이면 `1` 반환
  `n > 1` 이면 `n`과 `n-1` 의 요인 값을 반환
- `n`이 음수이면 `TypeError`

```js
const factorial = (n) =>
  n < 0
    ? (() => {
        throw new TypeError("Negative numbers are not allowed!");
      })()
    : n <= 1
    ? 1
    : n * factorial(n - 1);
```

### 예

```js
factorial(6); // 720
```
