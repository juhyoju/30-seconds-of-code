## Native JavaScript Data Structures

1. 배열은 요소의 집합을 나타나는 선형 데이터 구조이다.
2. JavaScript에는 배열의 크기가 고정되어 있지 않지만, 배열 자체도 유효한 유형일 수 있다.
3. 배열은 가장 일반적으로 사용되는 데이터 구조이며, 콘텐츠를 쉽게 조작하거나 변형할 수 있는 많은 방법이 있다.

```js
const nums = [1, 2, 3];
const strs = Array.from("est");

nums.push(6);
nums.push(4, 9);
strs.unshift("t");

nums.length; // 6
nums[nums.length - 1]; // 9
strs[0]; // 't'
strs[2]; // 's'

nums.slice(1, 3); // [2, 3]
nums.map((n) => n * 2); // [2, 4, 6, 12, 8, 18]
nums.filter((n) => n % 2 === 0); // [2, 6, 4]
nums.reduce((a, n) => a + n, 0); // 25

strs.reverse(); // ['t', 's', 'e', 't']
strs.join(""); // 'test'
```

<br>

### Sets

- 집합은 정렬된 고유 값 집합을 나타내는 `선형 데이터 구조` 이다.
- JavaScript의 `sets`는 모든 유효한 유형의 값을 저장할 수 있지만 각 값은 `값 동등성 검사에 따라 한 번만 실행`할 수 있다.

```js
const nums = new Set([1, 2, 3]);

nums.add(4);
nums.add(1);
nums.add(5);
nums.add(4);

nums.size; // 5
nums.has(4); // true

nums.delete(4);
nums.has(4); // false

[...nums]; // [1, 2, 3, 5]

nums.clear();
nums.size; // 0
```

<br>

### Maps

- 요소의 키 집합을 나타내는 `결합 데이터 구조`이다.
- JavaScript의 `map`은 각 키의 고유하고, 원시값 또는 객체여야 하지만, 맵의 값은 유효한 모든 유형이 될 수 있다.

```js
const items = new Map([
  [1, { name: "John" }],
  [2, { name: "Mary" }],
]);

items.set(4, { name: "Alan" });
items.set(2, { name: "Jeff" });

items.size; // 3
items.has(4); // true
items.get(2); // { name: 'Jeff' }

items.delete(2);
items.size; // 2

[...items.keys()]; // [1, 4]
[...items.values()]; // [{ name: 'John' }, { name: 'Alan' }]

items.clear();
items.size; // 0
```
