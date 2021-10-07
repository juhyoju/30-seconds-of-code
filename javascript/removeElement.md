## removeElement

DOM으로부터 요소를 제거하는 방법

1. `Element.parentNode`를 이용하여 요소의 상위 노드를 가져온다.
2. `Element.removeChild()`를 이용하여 상위 노드에서 지정된 요소를 제거한다.

```js
const removeElement = (el) => el.parentNode.removeChild(el);

/* Example */
removeElement(document.querySelector("#my-element"));
// Removes #my-element from the DOM
```
