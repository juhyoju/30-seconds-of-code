
## How do I empty an array in JavaScript?
- 배열을 비우거나 요소를 제거하는 방법
- 각 방법마다 장단점이 있다.


## 1. Assign it to an empty array
**새로운 빈 배열에 변수를 할당하는 방법**  

```javascript
let a = [1, 2, 3, 4];
a = [];
```
❗ 배열을 비우는 가장 빠르고 쉬운 방법  
❗ const 로 선언된 배열에는 작동하지 않는다.
❗ 원본 배열은 변경되지 않는다.

##### 참조
```javascript
let b = a;
a = [];
console.log(b); // [1,2,3]
```
- 먼저 변수 b는 a 배열을 참조한다.
- 그런 다음 a는 빈 배열에 할당된다.
- ✅ 원본 배열은 변경되지 않고 그대로 남아있는 문제가 발생한다.


<br>

## 2. Set its length to 0
**배열의 길이를 0으로 설정**

```javascript
let a = [1, 2, 3, 4];
a.length = 0;
```

❗ 배열을 비우는 매우 빠르고 좋은 방법
❗ 항상 변수에서 작업할 수 있는 장점이 있다.
❗ 배열의 길이를 0으로 설정하면 배열의 모든 요소가 자동으로 삭제된다.
❗ ES5에서 `strict mode` 할때도 배열의 길이는 읽기/쓰기 속성이므로 잘 작동한다.

<br>

## 3. Use Array.prototype.splice()
**splice 메서드를 이용하여 모든 요소 제거**

```javascript
let a = [1, 2, 3, 4];
a.splice(0, a.length);
```

❗ a 배열의 모둔 요소를 제거하고 제거된 요소를 배열로 반환한다.
❗ 다른 방법에 비해 단점은 없지만 성능이 떨어진다.

<br>

## 4. Use Array.prototype.pop()
**while루프와 pop 메서드를 사용하여 배열의 각 요소를 하나씩 제거**

```javascript
let a = [1, 2, 3, 4];
while (a.length) a.pop();
```

❗ 구식 옵션으로, 장황하고 성능이 떨어진다.