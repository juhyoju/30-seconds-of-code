
## Navigation list item hover and focus effect
네비게이션 아이템 마우스 오버 시에니매이션 효과 주기!

```html
<nav class="hover-nav">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```
```css
.hover-nav li a {
	position: relative;
	padding: 25px 12px;
	display: inline-block;
}

li a:before {
	position: absolute;
	content: "";
	width: 100%;
	height: 100%;
	bottom: 0;
	left: 0;
	background-color: #f6c126;
	z-index: -1;
	transform: scale(0);
	transition: transform 0.5s ease-in-out;
}

li a:hover:before,
li a:focus:before {
	transform: scale(1);
}
```


## transform : scale()
- 요소를 소를 확대 또는 축소할 수 있다.
- 1보다 큰 수는 **확대** / 1보다 작은 수는 **축소**

```css
transform: scale( 2.0, 1.5 ); /* 가로 2배, 세로 1.5배 확대 */
transform: scaleX( 2.0 ); /* 가로 2배 확대 */
transform: scaleY( 1.5 ); /* 세로 1.5배 확대 */
```
