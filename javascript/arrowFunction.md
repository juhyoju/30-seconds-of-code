## arrow function 소개
- ES6에서 정의한 문법이며, 익명 함수 선언 방식으로 간결하게 코드를 작성할 수 있다.
- 일반적으로 () => {} 표현한다.
- this, arguments 를 바인딩하지 않는다.

### 1. 구문
화살표 함수를 이해하기 위해서는 일반 함수로 리팩토링 하는 것부터 시작해야한다.
```js
function square(a) {
  return a * a;
}
```

#### 1-1. 변수 할당을 위한 함수 선언을 한다. 
```js
const square = function (a) {
  return a * a;
}
```

#### 1-2. 일반 함수를 화살표 함수로 리팩토링 한다.
```js
const square = (a) => {
  return a * a;
}
```

#### 1-3. 변수가 하나만 있다면, 소괄호를 생략할 수 있다.
```js
const square = a => {
  return a * a;
}
```

#### 1-4. 함수가 단일식이라면, 중괄호 및 반환문을 생략하고 암시적 반환을 할 수 있다.
```js
const square = a => a * a;
```


<hr>


### 2. 실행 컨텍스트
화살표 함수와 일반 함수의 가장 큰 차이점은 this 이다.

#### 2-1. 일반 함수의 this
- **함수 호출 방식**에 따라 this에 바인딩할 어떤 객체가 **동적으로 결정**된다.  
다시 말해, 함수를 선언할 때 this에 바인딩할 객체가 정적으로 결정되는 것이 아니고, 함수를 호출할 때 함수가 어떻게 호출되었는지에 따라 this에 바인딩할 객체가 동적으로 결정된다.  
- 전역객체에 바인딩되며, 브라우저 환경에서 전역객체는 `window`, Node.js 환경에서는 `global`이다.
- 콜백 함수 내부의 this가 메소드를 호출한 객체(생성자 함수의 인스턴스)를 가리키게 하려면 `Function.protype.bind()`를 사용하거나 화살표 함수를 사용하여 해결할 수 있다.

```js
function simple() { return this; }
const object = {
  method() { return this; }
};
class Class {
  classMethod() { console.log(this); }
}
const instance = new Class();

simple();                   // `this` refers to the global object
new simple();               // `this` refers to the newly created instance

object.method();            // `this` refers to `object`
simple.call(object);        // `this` refers to `object`

instance.classMethod();     // `this` refers to `instance`
setTimeout(
  instance.classMethod, 0   // `this` refers to the global object
);
```


#### 2-2. 화살표 함수의 this
- 함수를 선언할 때 this에 바인딩할 객체가 정적으로 결정된다.
- 화살표 함수의 this는 `언제나 상위 스코프의 this`를 가리키며, `Lexical this`라고 한다.
- prototype property를 갖지 않기 때문에 생성자 함수로 사용할 수 없다.

```js
const simple = () => this;
const object = {
  method: () => this
};
class Class {
  classMethod = () => { console.log(this); }
}
const instance = new Class();

simple();                   // `this` refers to the global object
new simple();               // Uncaught TypeError: simple is not a constructor

object.method();            // `this` refers to the global object
simple.call(object);        // `this` refers to the global object

instance.classMethod();     // `this` refers to `instance`
setTimeout(
  instance.classMethod, 0   // `this` refers to `instance`
);
```


<hr>

### 주의

❗❗ 화살표 함수는 Lexical this를 지원하므로 콜백 함수로 사용하기 편리하지만 화살표 함수를 사용하는 것이 오히려 혼란을 불러오는 경우도 있으므로 주의하여야 한다.