

## Drop cap

```html
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam commodo ligula quis tincidunt cursus. Integer consectetur tempor ex eget hendrerit. Cras facilisis sodales odio nec maximus. Pellentesque lacinia convallis libero, rhoncus tincidunt ante dictum at. Nullam facilisis lectus tellus, sit amet congue erat sodales commodo.</p>
```
```css
p::first-letter {
  color: #5f79ff;
  float: left;
  margin: 0 8px 0 4px;
  font-size: 3rem;
  font-weight: bold;
  line-height: 1;
}
```

## ::First-letter
- 요소의 첫번째 문자를 선택하는 선택자  
- 블록 요소에만 적용 가능 (display 값 : block, list-item, table-cell, inline-block. table-caption 일 때)

#### 속성
`margin, padding, border, color, background,`  
`text-decoration, text-transform, letter-spacing, word-spacing, line-height, float, clear, vertical-algin (float:none 일 경우)`


#### 결과
![image](https://user-images.githubusercontent.com/47467774/119441779-a6a15380-bd61-11eb-8bdf-cffa252b25c5.png)

