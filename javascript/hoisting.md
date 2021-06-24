
## What is hoisting in JavaScript?

  

### hoisting 이란?
- 코드에 선언된 변수 및 함수(var, left, const, function 등)를 **유효 범위의 최상단**으로 끌어올리는 것을 말한다.
- 변수 범위가 `전역 범위`인지 `함수 범위`인지에 따라 다르게 수행될 수 있다.
-  **함수 범위(function scope)** : 해당 함수의 최상단으로
-  **전역 범위(global scope)** : 스크립트 단위의 최상단으로
- ❗ 할당 내용이 아닌 `선언`들만 모두 최상단으로 끌어 올려진다.
- ❗ 실제로 코드가 끌어올려지는 건 아니며, 자바스크립트 Parser 내부적으로 끌어올려서 처리하는 것이다.
- ❗❗ **'유효범위의 코드가 실행되기 전, 메모리에 저장했던 선언문을 먼저 사용한다'** 는 의미
  

<br>

  

## hoisting 대상

var 변수 선언과 함수선언문에서만 호이스팅이 일어난다.  

#### 1. function
함수는 함수 선언문 방식일때만 Hoisting이 되며, 함수 자체가 hoisting이 된다.  
❗ 함수 선언문을 제외한 방식들은 변수선언과 같이 함수 자체가 아직 선언이 되지 않아서 오류가 발생한다.

```js
hello(); // logs 'Hello world!'  

function  hello() {
   console.log('Hello world!');
}
hello(); // logs 'Hello world!'
```

위 예제가 실제로 실행될 때에는 아래와 같이 함수 자체가 끌어올려진다.

```js
function  hello() {
   console.log('Hello world!');
}

hello(); // 'Hello world!' 
hello(); // 'Hello world!'
```

  

#### 2. var

##### 2-1 일반적인 방법
```js
var  a = 'Hi!';
console.log(a); // returns 'Hi!'
```

##### 2-2 undefined
var 선언은 해당 범위의 맨 위에 호이스팅되지만 초기화 전에 액세스하면 정의되지 않은 상태(undefined)로 반환된다.

```js
console.log(a); // undefined
var  a = 'Hi!';
```

  

##### 2-3 var hoisting
```js
console.log(x); // undefined
f(); // throws 'Uncaught TypeError: f is not a function'  

var  x = 1;
var  f = () =>  'Hi!'; 

console.log(x); // logs '1'
f(); // Hi!
```

  
  

#### 3. const and let
const, let도 호이스팅은 되지만 액세스 문제로 Reference Error가 발생한다.


```js
console.log(y); // throws 'Uncaught ReferenceError: Cannot access "y" before initialization'
g(); // throws 'Uncaught ReferenceError: Cannot access "g" before initialization'

let  y = 2;
const  g = () =>  'Hey!';  

console.log(y); // logs '2'
f(); // returns 'Hey!'
```

<br>

## 주의할 점
- 코드의 가독성과 유지보수를 위해 hoisting이 일어나지 않도록 한다.
- 변수 및 함수 등 사용 전 코드 상단부에 선언하여 hoisting을 방지한다.
- let과 const를 사용한다.