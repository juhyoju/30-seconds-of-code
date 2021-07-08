## isAsyncFunction

- 주어진 인수가 비동기식 함수인지 판별한다.  
- `Object.prototype.toString()` 과 `Function.prototype.call()` 를 이용하여 확인한다.

```js
const isAsyncFunction = val =>
  Object.prototype.toString.call(val) === '[object AsyncFunction]';
  ```

  

  ### Object.prototype.toString()
- toString() 은 문자열을 반환하는 object의 대표적인 방법이다.
- 인자를 취하지 않고 문자열을 반환한다.
- 원하는 어떤 값이든 될 수 있지만 해당 객체에 대한 정보를 전달하고 있을 때 가장 유용하다.

```js
var o = new Object();
o.toString(); // returns [object Object]
```

### Function.prototype.call()
- apply()와 거의 동일하지만 call()은 `인수 목록`을, apply()는 `인수 배열 하나`를 받는다.
- 이미 할당되어있는 다른 객체의 함수/메소드를 호출하는 해당 객체에 재할당할때 사용된다.
