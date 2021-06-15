## currentURL
```javascript
const currentURL = () => window.location.href;
```

```javascript
currentURL(); // 'https://www.google.com/'
```

## window.location
#### 1. `window.location.href`
현재 페이지의 위치를 ​​반환한다.
```javascript
console.log(window.location.href); 
// https://www.google.com/webhp?hl=ko&sa=X&ved=0ahUKEwjunM3am5nxAhWm3mEKHeeaDSkQPAgI
```

<br>

#### 2. `window.location.hostname`
URL의 도메인 부분을 값으로 한다.
```javascript
console.log(window.location.hostname);
// https://www.google.com
```

<br>

#### 3.  `window.loactoin.protocol`
URL의 포로토콜 부분을 값으로 하며, 마지막의 `':'`도 포함한다.
```javascript
console.log(window.location.protocol);
// https:
```