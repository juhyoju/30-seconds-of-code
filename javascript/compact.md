## compact
```javascript
const compact = arr => arr.filter(Boolean);

/* Examples */
compact([0, 1, false, 2, '', 3, 'a', 'e' * 23, NaN, 's', 34]); 
// [ 1, 2, 3, 'a', 's', 34 ]
```

## Array.prototype.filter()
filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환한다.  
어떤 요소도 테스트에 통과하지 못할 경우 빈 배열을 반환한다.

```javascript
/* Example*/
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter(word => word.length > 6);
console.log(result); // Array ["exuberant", "destruction", "present"]
```

## boolean
`참(true)` 혹은 `거짓(false)` 값만을 가질 수 있는 논리적 데이터 유형이다.  
  
자바스크립트에서 불린 조건은 아래와 같은 경우에 쓰인다.
- 어떤 코드 부문이 실행되어야 할 지(예를 들어 if절 안에서) 
- 어떤 코드 부문을 반복해야 할지(예를 들어 for문 안에서) 

## 거짓 같은 값 (Falsy, falsey)
boolean 문맥에서 `false` 로 변환되는 값이다.  
자바스크립트는 조건문, 반복문 등 boolear값이 필요한 곳에서 형 변환을 이용하여 특정 값을 boolean 값으로 변환한다.

#### 8가지 거짓 같은 값들
1. `false` : 키워드 false
2. `0` : 숫자 0
3. `-0` : 음수 0
4. `0n` : BigInt , boolean 으로 사용될 경우, 숫자와 같은 규칙을 따름
5. `" "` : 빈 string
6. `null` : 아무런 값도 없음
7. `undefined` : 원시값
8. `NaN` : 숫자가 아님