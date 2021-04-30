# HTML 요소에 스타일 추가하기
``` javascript
const addStyles = (el, styles) => Object.assign(el.style, styles);

addStyles(document.getElementById('my-element'), {
  background: 'red',
  color: '#ffff00',
  fontSize: '3rem'
});
```
<br>

## Object.assign() 메소드
```javascript
Object.assign(target, ...sources)
```
- **target** : 대상 객체
- **sources** : 출처 객체
- 여러 개의 객체 중 target 객체에 sources 객체의 속성을 병합/복사하고 target 객체를 반환한다.

####  예제
```javascript
const target = {a : 0 , b : 1};
const source= {b : 2, c : 3};

Object.assign(target, source);
// target = {a: 0, b: 2, c: 3}
```

<br>

## Element.style 속성
- 해당 엘리먼트에게 **새로운 스타일을 설정**하는 데 사용한다.
- **오직 인라인 스타일**에만 적용된다.
- **element.style.propertyName**

``` javascript
const element = document.getElementById("아이디"); // 특정 엘리먼트 노드 가져오기  
const style = element.style; // 해당 엘리먼트에 적용된 스타일 가져오기
```
<br>

> **외부선언된 엘리먼트의 스타일을 아이디를 통해 지정하긴 했어도, 적용되지 않는 이유**
DOM 영역의 노드들이 브라우저에 그려질 때, 
외부에 선언된 스타일을 참조하여 브라우저에 그려지는 것이지, 
실제로 DOM 영역의 해당 노드들에게 속성으로 적용하는 것이 아니기 때문이다.
그래서 style 키워드는 해당 DOM의 노드를 직접 가져오는 것이기 때문에,
브라우저에는 스타일이 적용된 채로 그려지지만 노드 자체에는 스타일 값이 없는 것이다.
*<참고>  https://helloinyong.tistory.com/284*
