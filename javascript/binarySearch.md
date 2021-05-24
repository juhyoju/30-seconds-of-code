## binarySearch

- 이진 탐색은 순차 탐색에 비해 엄청나게 빠른 속도로 원하는 데이터를 찾을 수 있다.  
 - 이진 탐색은 매우 빠른 속도로 데이터를 찾을 수 있지만 반드시 데이터가 정렬되어 있어야만 한다.
 - Big O 표기법으로 **O(log n)** 이라고 표기한다.
 - 정렬된 배열에서 지정된 요소의 인덱스를 찾는다.

```javascript
const binarySearch = (arr, target) => {
  let low = 0,
    high = arr.length - 1;
  while (low <= high) {
    const mid = Math.floor((low + high) / 2);
    const guess = arr[mid];
    
    if (guess === target) return mid;
    
    if (guess > target) high = mid - 1;
    else low = mid + 1;
  }
  return -1;
};
```

<br>

## 이진탐색 
- low가 high보다 작거나 같으면  지정된 요소의 인덱스를 찾을 때까지 반복하여 범위를 좁혀간다. (while문)
  >  target이 mid를 인덱스로 가지는 배열의 요소보다 크다면, mid+1 ~ high 까지만 탐색한다
  > target이 mid를 인덱스로 가지는 배열의 요소보다 작다면, low ~ mid까지만 탐색한다.

- **[반복]** mid는 배열의 중앙 인덱스를 저장한다. ((low + high ) / 2 )
     이렇게 target쪽으로 포커스를 좁혀가며 배열을 반씩 나누다 보면 배열의 길이가 1이 된다.
- 배열의 범위가 좁혀질 때, guess가 target의 값과 동일하다면 해당 요소의 인덱스를 반환하고
배열의 요소가 target과 다르다면 -1 을 반환한다.

<br>

##### example
```javascript
binarySearch([1, 2, 3, 4, 5], 1); // 0
binarySearch([1, 2, 3, 4, 5], 5); // 4
binarySearch([1, 2, 3, 4, 5], 6); // -1
```