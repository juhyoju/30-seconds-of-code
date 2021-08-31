## JavaScript Data Structures - Stack

### 정의

- 스택(Stack)은 데이터를 넣을 수 있는 선형(linear) 자료구조이다.
- LIFO(Last In, First Out) 작업 순서를 따른다.

`IN -> [pear, orange, apple]`  
`OUT <- [pear, orange, apple]`

<br>

### 데이터 구조의 작업

1. `qush` : stack 가장 위 쪽에 데이터 요소 추가
2. `pop` : stack 가장 윗 쪽부터 데이터 요소 삭제
3. `peek` : stack의 가장 윗 쪽의 데이터 요소를 삭제하지 않고 검색
4. `isEmpty` : stack이 비었는지 확인

<br>

### 구현

```js
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.unshift(item);
  }

  pop(item) {
    return this.items.shift();
  }

  peek(item) {
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }
}
```

1. 각 인스턴스에 빈 배열인 `items`을 초기화하는 `constructor`로 `class`를 생성한다.
2. `push` 메소드 : `Array.prototype.unshift()` 를 이용하여 배열 `items`의 가장 시작 부분에 요소를 추가한다.
3. `pop` 메소드 : `Array.prototype.shift()` 를 이용하여 배열 `items`의 가장 시작 부분부터 요소를 삭제한다.
4. `peek` 메소드 : `items` 배열에서 데이터를 삭제하지 않고 첫 번째 요소의 값을 검색한다.
5. `isEmpty` 메소드 : `Array.prototype.length` 를 이용하여 배열 `items` 가 빈 배열인지 확인한다.

```js
const stack = new Stack();

stack.push("apples");
stack.push("oranges");
stack.push("pears");

stack.isEmpty(); // false

stack.peek(); // 'pears'

stack.pop(); // 'pears'
stack.pop(); // 'oranges'
stack.pop(); // 'apples'

stack.isEmpty(); // true
```
