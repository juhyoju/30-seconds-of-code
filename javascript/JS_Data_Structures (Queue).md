## JavaScript Data Structures - Queue

### 정의

- 큐(Queue)는 데이터를 넣을 수 있는 선형(linear) 자료구조이다.
- 선입선출(FIFO) 작업 순서의 특징을 갖는다.

`IN -> [E, D, C, B, A] -> OUT`

<br>

### 데이터 구조의 작업

1. `enqueue` : queue 제일 끝에 데이터 요소 추가
2. `dequeue` : queue 시작 앞쪽에 데이터 요소 제거/추출
3. `peek`: 데이터 요소를 삭제하지 않고 queue의 시작 부분에 있는 요소 검색
4. `isEmpty` : queue가 비었는지 체크

<br>

### 구현

```js
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(item) {
    this.items.push(item);
  }

  dequeue(item) {
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
2. `enqueue` 메소드 : `Array.prototype.push()` 를 이용하여 배열 `items`의 가장 끝에 요소를 추가한다.
3. `dequeue` 메소드 : `Array.prototype.shift()` 를 이용하여 배열 `items`의 가장 처음에서 요소를 삭제한다.
4. `peek` 메소드 : `items` 배열에서 데이터를 삭제하지 않고 첫 번째 요소의 값을 검색한다.
5. `isEmpty` 메소드 : `Array.prototype.length` 를 이용하여 배열 `items` 가 빈 배열인지 확인한다.

```js
const queue = new Queue();

queue.isEmpty(); // true

queue.enqueue("A");
queue.enqueue("B");
queue.enqueue("C");
queue.enqueue("D");
queue.enqueue("E");

queue.isEmpty(); // false

queue.peek(); // 'A'

queue.dequeue(); // 'A'
queue.dequeue(); // 'B'
queue.dequeue(); // 'C'

queue.peek(); // 'D'
```
