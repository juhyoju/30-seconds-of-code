## 'this' 란 무엇인가?

`this` 는 일반적으로 함수를 호출하는 객체이다.  

- this는 전역 객체(브라우저에서 window)를 참조한다. (예외: 'use strict')
- 일반 함수 또는 내부 함수의 this는 전역 객체를 참조한다.
- 객체 메서드 또는 프로토타입 메서드에서 this는 해당 메서드를 호출한 객체를 참조한다.
- 생성자 함수 내부의 this는 생성된 객체를 참조한다.
- DOM event handler로 사용되는 함수 내부의 this는 이벤트가 발생한 element로 설정된다.


<br>

## 1. 전역에서의 this
✅ 전역 실행 컨텍스트에서의 this는 strict mode와 관계없이 `전역객체` 참조

```js
console.log(this); // window
```

## 2. 일반 함수의 this
함수 내부에서 this의 값은 **함수 호출 방법**에 의해 달라진다.

### 2-1. 단순 호출
✅ 일반 함수에서의 this는 `window` 

```js
function f() {
  return this;
}

console.log(f()); // window
```

### 2-2. strict mode
✅ strict mode 에서는 `undefined`  
strict mode에서 this는 실행 문맥에 진입하여 설정되는 값을 유지하기 때문

```js
'use strict'; 

function f() {  
  return this;
}

console.log(f()); // undefined
```


## 3. Object context의 this

### 3-1. 객체 메서드
✅ 함수를 어떤 객체의 메서드로 호출하면 this는 `그 객체`

```js
const obj = {
  f: function() {
    return this;
  }
};

const myObj = Object.create(obj);
myObj.foo = 1;

console.log(myObj.f()); // { foo: 1 }
```

### 3-2. 생성자 함수
✅ 생성자 함수로 객체를 생성할 때, 생성자 함수의 this는 `새로 생성된 객체`

```js
class C {
  constructor() {
    this.x = 10;
  }
}

const obj = new C();
console.log(obj.x); // 10
```

## 4. 화살표 함수의 this
✅ 화살표 함수에서 this는 싸여진 `lexical context`이고, 전역 코드에서는 `전역 객체`를 가리킨다.

```js
const f = () => this;

console.log(f() === window); // true

const obj = {
  foo: function() {
    const baz = () => this;
    return baz();
  },
  bar: () => this
};

console.log(obj.foo()); // { foo, bar }
console.log(obj.bar() === window); // true
```

## 5. event handler에서의 this
✅ 함수를 evnet handler로 사용할 때, this는 `이벤트를 발생시킨 요소`

```js
const el = document.getElementById('my-el');

el.addEventListener('click', function() {
  console.log(this === el); // true
});
```

## 6. 바인딩 this
bind, call, apply를 이용하면 this를 원하는 객체에 연결할 수 있다.

### 6-1. bind
✅ `Function.protype.bind()` 를 이용하여 기존 함수를 가진 새로운 함수를 생성한다.  
✅ 새 함수의 this는 호출 방식과 상관없이 영구적으로 bind()의 첫번째 매개변수로 고정한다.

```js
function f() {
  return this.foo;
}

var x = f.bind({foo: 'hello'});
console.log(x()); // 'hello'
```


### 6-2. call, apply
✅ 호출된 함수 중 매개변수로 받은 첫 번째 값은 함수 내부에서 사용되는 this에 바인딩된다.


```js
function f() {
  return this.foo;
}

console.log(f.call({foo: 'hi'})); // 'hi'
```

<br>
- apply() : 인수 목록을 받는다.
- call() : 인수 배열을 받는다.


아래 두 생성자 함수가 있다고 가정했을 때, this.name과 this.level을 받아오는 부분이 똑같다.

```js
function Character(name, level) {
  this.name = name;
  this.level = level;
}
 
function Player(name, level, job) {
  this.name = name;
  this.level = level;
  this.job = job;
}
```

apply() 사용
```js
function Character(name, level) {
  this.name = name;
  this.level = level;
}
 
function Player(name, level, job) {
  Character.apply(this, [name, level]);
  this.job = job;
}
 
var me = new Player('Nana', 10, 'Magician');
```

call() 사용
```js
function Character(name, level) {
  this.name = name;
  this.level = level;
}
 
function Player(name, level, job) {
  Character.call(this, name, level);
  this.job = job;
}
 
var me = {};
Player.call(me, 'nana', 10, 'Magician');
```



