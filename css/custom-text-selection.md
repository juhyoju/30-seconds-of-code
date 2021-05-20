
## Custom text selection

```html
<div>Select some of this text.</div>
<p>Select some of this text.</p>
```
```css
::selection {
  background: black;
  color: deeppink;
}
p::selection {
  background: skyblue;
  color: red;
}
::-moz-selection { }  /* Mozilla 계열(firefox) */
```

## ::selection 
- 선택된 영역의 스타일을 변경하게 도와주는 css 속성

#### 허용가능한 속성
- color
- background-color
- text-decoration
- text-shadow
- stroke-color, fill-color, stroke-width
> **background-image** 무시된다.


<br>