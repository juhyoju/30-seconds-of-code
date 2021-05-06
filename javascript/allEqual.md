# # allEqual
``` javascript
const allEqual = arr => arr.every(val => val === arr[0]);

allEqual([1, 2, 3, 4, 5, 6]); // false
allEqual([1, 1, 1, 1]); // true

/* one-line */
[1,1,1,1].every( (val, i, arr) => val === arr[0] )
```

## allEqual()

-  Array.prototype.every() 를 이용하여 배열의 요소가 해당 조건에 부합하는지 체크한다.
- 배열의 모든 요소가 arr[0] 첫번째 요소와 동일한지 체크한다.




<br>

## Strict equality ( === )
두 피연산자가 같은지 확인하여 부울 결과를 반환한다.

- 피연산자가 다른 유형이면 `false` 반환
- 피연산자가 `NaN`이면을 `false`반환 
- 두 피연산자의 값 비교
	+ 동일한 값의 `숫자`
	+ 동일한 `순서`의 동일한 `문자`　
	+ 둘 다 true 또는 false
 

 
#### 항등연산자(==)와 다른 점
- == 연산자 : 피연산자가 서로 다른 타입일 경우 **타입을 강제로 변환하여 비교**
- === 연산자 : **서로 동일한 타입의 동일한 값** 일 때만 true 반환

> === 연산자
>  **더 엄격하게** 자료형과 값을 비교한다.
> 자료형을 임의로 변환하지 않는다.


```javascript
console.log( "hi" === "hello" ); //false
console.log( null === null); // true
console.log( null === undefined ); // false
console.log( "3" === 3 ); // false

console.log( 0  ===  false  ); //false (동일 유형 아님)
console.log( 0  ==  false  ); //true ( == 와 === 의 차이) 
/* == 연산자는 0과 false 구분하지 못한다 */

console.log( 0 == '' ); // true
console.log(1 == true ); // true
```

