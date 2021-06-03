
## Image text overlay
```html
<div>
  <h3 class="text-overlay">Beautiful!</h3>
  <img src="https://source.unsplash.com/random/450x400" alt="random image">
</div>
```
```css
div {
  position: relative;
}

.text-overlay {
  position: absolute;
  top: 0;
  left: 0;
  padding: 1rem;
  color: white;
  backdrop-filter: blur(14px) brightness(80%);
}
```


## backdrop-filter 
요소 뒤 영역에 흐림이나 색상 시프트 등 그래픽 효과를 적용할 수 있는 속성


```css
backdrop-filter: blur(2px);
backdrop-filter: brightness(60%);
backdrop-filter: contrast(40%);
backdrop-filter: drop-shadow(4px 4px 10px blue);
backdrop-filter: grayscale(30%);
backdrop-filter: hue-rotate(120deg);
backdrop-filter: invert(70%);
backdrop-filter: opacity(20%);
backdrop-filter: sepia(90%);
backdrop-filter: saturate(80%);
```

<br>

##### 결과
![image](https://user-images.githubusercontent.com/47467774/120607632-53c74a80-c48b-11eb-9c87-7e933b2517d7.png)

