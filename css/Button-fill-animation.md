## Button fill animation
``` html
<button class="button">마우스 오버 시 배경색, 보더색, 폰트 컬러가 변하는 버튼</button>
```
```css
.button {
	padding:15px;
	background:red;
	border:3px solid black;
	color:white;
	cursor:pointer;
	transition:0.3s all ease-in-out;
}
.button:hover {
	background:yellow;
	border-color:red;
	color:blue;
}
```
## 링크 가상 클래스
CSS 링크 의사 클래스

``` 
스타일 적용 순서 : link → visited → hover → active
```

- :link : 방문 전 링크
- :visited : 방문 후 링크
- :active : 마우스 클릭할 때
- :hover :마우스 오버했을 때

<hr>

### 1. :hover

- **마우스 커서가 해당 요소를 가리키고 있을 때**의 링크 상태
-  ❗❗ 주의 : 터치스크린에서는 요소를 터치 직후, 또는 터치한 이후 다른 요소를 다시 터치하기 전까지 활성화되는 등 문제가 있다.
``` css
.a:hover {
	background:yellow;
	border-color:red;
	color:blue;
}
```
✔  a링크에 마우스 오버 :  a 태그의 배경색은 노랑, 보더 컬러는 빨강, 폰트 컬러는 파랑

 <hr>
 
### 2.  :link
- **방문 전** 링크 상태
- 링크를 가진 a 요소에 적용 
- 방문 여부에 상관없이 요소를 선택하려면 ``:any-link`` 사용

```css
a {
	color:red;
}
a:link {
	color:yellow;
}
 ```
✔  a링크에 방문 전 :  a 태그의 컬러는 노랑


 <hr>
 
### 3.  :visited 
- **방문 한 적이 있는** 링크 상태
- ❗❗ 주의 : 개인정보 보호를 위해 :visited 에서 사용할 수 있는 스타일이 제한된다.
```css
a:visited {
	color:green;
	border-color:blue;
	background-color:red;
}
 ```
 ✔  a링크에 방문 후 :  a 태그의 컬러는 초록, 보더 컬러는 파랑, 배경색은 빨강

 <hr>
 
### 4.  :active
- **마우스를 클릭할 때**의 링크 상태
- 마우스를 활용하여 버튼을 누르는 순간부터 떼는 시점까지를 의미
```css
a:active {
	color:white;
}
 ```
✔  a링크를 클릭할 때부터 떼는 순간까지 : a 태그의 컬러는 하양


<br>

## transition

css 속성을 변경할 때 애니메이션 효과를 줄 수 있다.

### 문법
```css
div {
    transition: <property> <duration> <timing-function> <delay>;
}
```

### 예제
```html
<div class="transition">애니메이션 효과</div>
``` 
```css
.transition {
	padding:15px;
	background-color:red;
	border:3px solid black;
	color:white;
	cursor:pointer;
    transition:background-color 2s, border-color 2s, color 2s;
    /* 한번에 표현 가능*/
    transition:all 2s ease-in-out;
}
.transition:hover {
	background-color:yellow;
	border-color:red;
	color:blue;
}
```