
## Box-sizing reset
```css
box-sizing: content-box | border-box | initial | inherit;
/* 기본값 content-box */
```

- **content-box** : 패딩, 보더 값이 콘텐츠 크기에 미포함 (지정한 박스 크기와 상이)
- **border-box** :  요소의 너비(또는 높이)값에 패딩과 보더값이 포함되어 크기 변경 X
- initial : 초기값
- **inherit** : box-sizing property를 부모요소에서 자식요소로 상속

<br>

## content-box와 border-box
- box-sizing 속성값에 따라 div 박스의 크기가 달라진다.
```html
<div class="content-box"></div>
<div class="border-box"></div>
```
```css
div {
	width:100px;
	height:100px;
	padding:20px;
	border:10px solid blue;
}
.content-box {
	box-sizing:content-box;
}
.border-box {
	box-sizing:border-box;
}
```

#### 결과
![image](https://user-images.githubusercontent.com/47467774/117139112-d3a7b980-ade6-11eb-9f6f-ede912798e2c.png)

**content-box** : width 160px / height 160px
> 가로값 : 100px  + 20px (좌측 패딩) + 20px (우측 패딩) + 10px (좌측 보더) + 10px (우측 보더)
> 


> 박스 바깥 쪽으로 보더가 생성되어 크기가 확장됨

 **border-box** : width 100px / height 100px
> 고정사이즈의 박스 영역 안 쪽으로 보더가 생성되어 박스 크기는 유지됨
