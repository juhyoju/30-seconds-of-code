
## cartesianProduct
```javascript
const cartesianProduct = (a, b) =>
  a.reduce((p, x) => [...p, ...b.map(y => [x, y])], []);

 /* example */  
 cartesianProduct(['x', 'y'], [1, 2]); // [['x', 1], ['x', 2], ['y', 1], ['y', 2]]
  ```

## cartesianProduct (데카르드 곱)

공집합이 아닌 집합들로부터 새로운 집합을 만드는 방법  
예) A = { a, b, c }, B = { 1,  2 } 일 때, A x B = { ( a,1 ) , ( a,2 ), ( b,1 ), ( b,2 ), ( c,1 ), ( c,2 )} 

<br>

## Array.prototype.map()
`map()` 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환한다.
```javascript
const array1 = [1, 2, 3, 4];
const map1 = array1.map(x => x * 2);

console.log(map1); // [2, 4, 6, 8] (* 2가 적용된 결과값 반환)
```
- `map`은 `callback` 함수를 **각각의 요소에 대해 한번씩** 순서대로 불러 그 함수의 반환값으로 새로운 배열을 만든다.
- (undefined도 포함해서) 배열 값이 들어있는 인덱스에 대해서만 호출한다.
- map은 `callback` 함수에 의해서 변형될 수는 있으나, 호출한 배열의 값을 변형하지 않는다.