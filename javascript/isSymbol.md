## isSymbol

 ```javascript
const  isSymbol = val  =>  typeof  val === 'symbol';
```

  

## typeof
피연산자의 평가 전 자료형을 나타내는 문자열을 반환한다.
typeof 연산자는 피연산자 앞에 존재한다.

```javascript
typeof(operand)
```
[**operand**] : 자료형을 가져올 객체 또는 원시값을 나타내는 표현식


#### `typeof`가 반환할 수 있는 값
1.  Undefined :  `"undefined"`
2. Null : `object`
3. Boolean : `boolean`
4. Number : `number`
5. BigIng : `bigint`
6. String : `string`
7. **Symbol** : `symbol` (ECMA 2015 추가)
8. 호스트객체 (JS 환경에서 제공) : 구현체마다 다름
9.  Function 객체 : `function`
10. 다른 모든 객체 : `object` 

```javascript
// Numbers
typeof 37 === 'number';
typeof 3.14 === 'number';
typeof Math.LN2 === 'number';
typeof Infinity === 'number';
typeof NaN === 'number';
typeof Number(1) === 'number'; // but never use this form!

typeof 42n === 'bigint';

// Strings
typeof "" === 'string';
typeof "bla" === 'string';
typeof (typeof 1) === 'string'; // typeof always returns a string
typeof String("abc") === 'string'; // but never use this form!

// Booleans
typeof true === 'boolean';
typeof false === 'boolean';
typeof Boolean(true) === 'boolean'; // but never use this form!

// Symbols
typeof Symbol() === 'symbol'
typeof Symbol('foo') === 'symbol'
typeof Symbol.iterator === 'symbol'

// Undefined
typeof undefined === 'undefined';
typeof declaredButUndefinedVariable === 'undefined';
typeof undeclaredVariable === 'undefined';

// Objects
typeof {a:1} === 'object';

// use Array.isArray or Object.prototype.toString.call
// to differentiate regular objects from arrays
typeof [1, 2, 4] === 'object';

typeof new Date() === 'object';


// The following is confusing. Don't use!
typeof new Boolean(true) === 'object';
typeof new Number(1) === 'object';
typeof new String("abc") === 'object';


// Functions
typeof function(){} === 'function';
typeof class C {} === 'function';
typeof Math.sin === 'function';
```