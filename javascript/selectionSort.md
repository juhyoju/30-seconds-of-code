## selectionSort

선택 정렬은 가장 작은 값을 탐색한 다음 Swap을 통해 앞부분에 배치시키는 정렬방식

1. 배열 중 최소값을 찾는다.
2. 최소값을 맨 처음의 index값과 swap 한다.
3. 맨 처음 index를 제외한 나머지 배열에 대해 1~2단계를 진행한다.
4. 하나의 요소가 남을 때까지 1~3단계를 반복한다.

👍 장점

- 알고리즘 구현 난이도가 굉장히 낮은 단순한 알고리즘이다.
- 주어진 공간 외 추가 메모리 공간이 필요없다. (= in place 알고리즘)

👇 단점

- 현재 값이 최소값인데도 불구하고 최소값을 찾기 위한 **불필요한** 순회 과정을 진행한다. (버블 정렬의 불필요한 배열의 이동을 줄여서 버블 정렬보다는 빠르다.)
- 최소값을 찾는 횟수가 정해져 있다. (n-1, n-2, ..., 1)
- 시간복잡도(O(n2))가 높아서 실제로는 잘 사용하지 않는다.
- 불안정 정렬(unstable sort)로써 동일한 값에 대해 기존의 순서가 뒤바뀔 수 있는 정렬 방식이다.

> ### Big-O
>
> Worst case : O(n2)
> Best case : O(n2)

<br>

## 소스코드

```javascript
const selectionSort = (arr) => {
  const a = [...arr];
  for (let i = 0; i < a.length; i++) {
    const min = a.slice(i + 1).reduce((acc, val, j) => (val < a[acc] ? j + i + 1 : acc), i);
    if (min !== i) [a[i], a[min]] = [a[min], a[i]];
  }
  return a;
};

/* Example */
selectionSort([5, 1, 4, 2, 3]); // [1, 2, 3, 4, 5]
```
