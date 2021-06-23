## Button shrink animation

button에 마우스 오버 시 0.8배 축소되는 애니메이션 효과  
```html
<button class="button-shrink">Submit</button>
```
```css
.button-shrink {
  color: #65b5f6;
  border: 1px solid #65b5f6;
  padding: 25px;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

.button-shrink:hover {
  transform: scale(0.8);
}
```

## transform: scale()
 - X 또는 Y축으로 확대/ 축소  
```css
transform:scaleX( x축 비율 ); // x축으로 확대, 축소
transform:scaleY( y축 비율 ); // y축으로 확대, 축소
transform:scale( x축 비율, y축 비율 ); // x축, y축으로 확대, 축소
```


##### 예시
```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```
```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: scale(0.7); /* scaleX(0.7) + scaleY(0.7) */
  background-color: pink;
}
```

##### 결과
![image](https://user-images.githubusercontent.com/47467774/123061939-0bc29480-d447-11eb-91c8-b8ba06c35dad.png)
