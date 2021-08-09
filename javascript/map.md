## map

- 함수를 사용하여 배열 값을 객체에 매핑한다.
- 배열(`arr`) 내의 각 요소에 주어진 함수(`fn`)을 적용하고 결과를 새로운 배열(객체)로 반환한다.
- 각 속성의 키로 `el`을 사용하고 값으로는 `fn`의 결과를 사용

```js
const mapObject = (arr, fn) =>
    arr.reduce((acc, el, i) => {
        acc[el] = fn(el, i, arr);
        return acc;
    }, 
{});

mapObject([1, 2, 3], a => a * a); // { 1: 1, 2: 4, 3: 9 }
```

### 구문
`arr.map(callback(currentValue[, index[, array]])[, thisArg])`

- currentValue : 처리할 현재 요소
- index (optional) : 처리할 현재 요소의 인덱스
- array (optional) : map()을 호출한 배열
- thisArgs (optional) : callback을 실행할 때 this로 사용되는 값
- **반환값** : 배열의 각 요소에 대해 실행한 callback의 결과를 모두 모은 새로운 배열

