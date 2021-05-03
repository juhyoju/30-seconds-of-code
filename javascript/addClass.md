
# HTML 요소 클래스 추가
```javascript
const addClass = (element, className) => element.classList.add(className);
addClass(document.querySelector('p'), 'special');
```

## Element.classList
```javascript
const addClass = (element, className) => element.classList.add(className);
```

 - Element.classList의 반환형은 'DOMTokenList'
 - class 속성 이름을 DOMTokenList 객체로 반환 / 조작하는 프로퍼티
 - 엘리먼트의 클래스 목록에 접근하는 방식을 대체하는 간편한 방법

 ### classList 메소드

```javascript
classList.add('classA')  : 클래스 하나 추가
classList.add('classA', 'classB', 'classC',)  : 클래스 여러개 추가
classList.remove('ClassD') : 클래스 하나 삭제
```


<br>

## querySelector()
.querySelector()는 CSS 선택자
```javascript
addClass(document.querySelector('p'), 'special');
```
해석 : 내 문서에 있는 첫번째 p 태그에 'special' 클래스를 추가한다.

<br>

 ❗❗ 주의 : 선택자에 해당하는 **첫번째 요소**를 반환한다. (없으면 null)


```html
 <body>
	<h1>첫번째 h1</h1> <!-- 이 것만 컬러 변경됨 -->
	<h1>두번째 h1</h1>
 </body>
 ```

``` javascript
document.querySelector( '.black' ).style.color = 'red';
```
<br>

## 연습
```html
<body>
	<h1 class="black">컬러가 바뀐다!</h1>
 </body>
```
```css
.black {color:#000}
.red {color:#ff0000;}
```
```javascript
const addClass = (el, className) => el.classList.add(className);
addClass(document.querySelector('.black'), 'red');
```
- 클래스명 .black인 첫번째 요소에 클래스 'red' 추가되어 컬러가 빨간색으로 변함
- 결과 이미지는 md 이미지 삽입 방법에 연구한 후 업데이트할 예정

