## elementIsFocused

지정된 요소에 포커스가 맞춰져 있는지 확인하는 방법

```js
const elementIsFocused = (el) => el === document.activeElement;
```

- `Document.activeElement` 를 이용하여 포커스 여부 확인

```js
elementIsFocused(el); // true if the element is focused
```
