## average
``` javascript
const average = (...nums) =>
  nums.reduce((acc, val) => acc + val, 0) / nums.length;

/* example */
average(...[1, 2, 3]); // 2
average(1, 2, 3); // 2
```


## reduce()
- reduce()는 배열의 각 요소에 대해 주어진 **리듀서(reducer)** 함수를 실행하고, 하나의 결과값 반환한다.
- reducer()는 `reduce(콜백함수, 초기값)` 의 형태이며, 배열의 각 요소가 주어진 `콜백함수`를 거치는데 이 콜백함수가 reducer이다.
- reducer()의 반환값은 각 요소가 리듀서를 거쳐 `acc`에 누적된 값의 결과값이다.
  


#### 리듀서 함수가 가지는 네 가지 인자
- **누산기(acc)** : 콜백함수(리듀서)의 반환값을 누적
만약 초기값이 제공된다면, 리듀서의 첫번째 호출 시 acc의 값은 초기값과 동일하지만, 초기값이 제공되지 않는다면 acc는 배열의 첫번째 값이 자동으로 들어간다.
- **현재값(cur)** : 현재 처리중인 배열의 요소
- **현재 인덱스(idx)** : 현재 처리중인 배열 index
초기값이 제공되지 않았다면  acc에 배열의 첫번째 값인 index 0의 값이 들어가고, idx는 index 1부터 시작하게된다.
- **원본 배열(src)** : reduce()를 호출한 배열


<br>

## initialValue
- 콜백함수를 처음 실행할 때, 누산기(acc)의 값
- 초기값은 반드시 입력하는 것이 좋다.


#### 초기값을 지정하면 
콜백함수를 처음 실행할 때, acc의 값은 initialValue가 되고, idx 0이 된다.

#### 초기값을 지정하지 않으면
콜백함수를 처음 실행할 때, acc의 값은 배열의 첫 번째 값(arr[0])이 되고, idx 는 1이 된다.

**발생할 수 있는 오류**
1. 배열의 첫번째 요소(0번 인덱스)를 accumulator에 누적한 후  **1번 인덱스부터 reducer를 거친다.**
2.  배열의 요소 값이 1개인데 초기값도 제공하지 않은 경우 or 초기값은 있지만 배열이 빈 배열인 경우에는 그 단독 값을 리듀서를 거치지 않고  **바로 반환한다.**
3.  배열이 비었는데 초기값도 없는 상태에서 reduce()를 호출하면  `TypeError`  오류가 발생한다.


```javascript
const sumCallback = ( acc, cur ) => { return acc + cur };

// 초기값 없이 reduce()실행할 경우 3가지
[1, 2, 3].reduce( sumCallback ); // 1 + 2 + 3 = 6 : 초기값이 없으므로 0번 인덱스를 accumulator에 누적
[1].reduce( sumCallback ); // 1 : 배열의 요소 값이 1개이고 초기값 X
[].reduce( sumCallback, 1 ); // 1 : 빈 배열에 초기값 1
[ ].reduce( sumCallback ); // TypeError
```

<br>


## 평균 구하기
```javascript
const arr = [1, 2, 3];

const result = arr.reduce(function add(sum, currValue) {
  return sum + currValue;
}, 0);
const average = result / arr.length;

document.writeln(average); // 2
```
1. reduce() 함수를 사용하여 배열의 합계를 구한다.
2. reduce() 함수의 파라미터로 전달되는 callback 함수는 누적값(sum), 현재 처리중인 배열의 element(currValue)를 파라미터로 받습니다. 
3. 누적값과 currValue의 합을 리턴하면, 배열의 다음값을 처리할 때, 이 리턴된 값이 callback 함수의 누적값(sum)으로 전달됩니다. 
4. 초기값은 0으로 지정하였습니다.
5. reduce() 함수를 사용하여 배열 element의 합을 구하고, 그 결과를 배열의 길이로 나누어서 배열 element의 평균값을 계산한다.

  