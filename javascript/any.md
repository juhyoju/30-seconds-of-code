## any
``` javascript
const any = (arr, fn = Boolean) => arr.some(fn);

any([0, 1, 2, 0], x => x >= 2); // true
any([0, 0, 1, 0]); // true
```

## Array.prototype.some()
```javascript
arr.some(callback(curentValue, index, array)[, thisArg])
```

<hr>

- **callback** : function 안에서 조건에 맞는게 하나라도 있는지 체크하며, true/false를 반환
- **curentValue** : 현재 요소 (ex. 반복문의 현재 요소)
- **index** : 현재 요소의 인덱스
- **array** :대상 배열
- **thisArg** : callback을 실행할 때 this로 사용하는 값

<hr>

- 배열 안의 **어떤 요소라도 조건에 부합하는 것이 있다면 true 반환**한다.
- 빈 배열의 경우 무조건 `false`를 반환
- 모두 `false`인 경우 `false` 반환
- 하나라도 true가 나오는 원소가 있으면 그 시점에서 배열의 순환을 끝내고 바로 true를 반환

####  예제
```javascript
const array = [1, 2, 3, 4, 5];

// 짝수의 값이 있는지 
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// 짝수 2,4가 있으므로 true 반환
```



## ❗❗ 확인
[Array.prototype.every()](https://github.com/juhyoju/30-seconds-of-code/blob/master/javascript/all.md)

Array 객체의 every() 와 some () 메서드는 모든 원소에 대해 실행하지 않는다.  

