
## byteSize
문자열 길이를 바이트 단위로 반환한다.


```javascript
const byteSize = str => new Blob([str]).size;

/* Example */
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```

## Blob
> Blob(Binary Large Object, 블랍)은 이미지, 사운드, 비디오와 같은 멀티미디어 데이터를 다룰 때 사용한다.  
데이터의 크기(Byte) 및 MIME 타입을 알아내거나, 데이터를 송수신을 위한 작은 Blob 객체로 나누는 등의 작업에 사용한다.

- 일련의 데이터를 처리하거나 간접 참조하는 객체이다.
- `Blob()` 생성자는 새로운 Blob 객체를 반환한다.
- 지정된 문자열을 Blob 객체로 변환한다.
 
 ## Blob.size 
 `Blob`  객체가 담은 데이터의 바이트 단위의 사이즈를 의미한다.
