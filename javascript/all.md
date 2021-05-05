# all
``` javascript
const all = (arr, fn = Boolean) => arr.every(fn);

all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```
<br>

## Array.prototype.every() 
```javascript
arr.every(function(currentValue, index, array), thisValue))
```
-  every()는 배열 안의 모든 요소를 검증하여 boolean 타입으로 반환한다.
- **모든 요소가 조건에 부합하면 true를 반환**한다.
- 하나라도 false이면 false를 반환한다.
- 빈 배열의 경우 무조건 true를 반환한다.

####  예제
```javascript
const array = [1, 2, 3, 4, 5];

arr.every(x => x < 10);
// true (array 배열의 모든 요소가 10보다 작다)
```
