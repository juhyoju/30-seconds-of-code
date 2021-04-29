# display:inline-block 정렬
```html
<div class="parent">
	<span class="child">1박스</span>
	<span class="child">2박스</span>
	<span class="child">3박스</span>
</div>
```
```css
.parent {
	width:600px;
	font-size:0;
}
.child {
	display: inline-block;
	width: calc(600px / 3);
	background:skyblue;
	font-size:15px;
}
```


## inline-block 속성
- inline-block은 inline과 block의 특성을 섞어놓았다고 이해하면 된다.
- inline-block의 속성을 가지는 요소에는 약 4px 정도의 여백이 생긴다. (여백이 생기는건 inline 특성)
- 태그와 태그 사이에는  `\r\n`  즉, 엔터라는 공백이 있고 이런 공백이 font-size에 영향을 받으면서  여백을 남긴다.  엔터치는 부분에 주석 처리를 하면 요소들간의 여백은 사라진다.
- 상위 요소의 class의 `font-size`를 0px로 해주면 공백이 사라지면서 자연스럽게 여백이 사라진다.

<br>

### 여백을 없애는 방법
1. 공백 제거
```html
<div class="parent">
	<!-- 이어붙인다 -->
	<span class="child">1박스</span>	<span class="child">2박스</span>
	
	<!-- 태그를 다음 줄에서 닫는다 -->
	<span class="child">1박스</span
	><span class="child">2박스</span>
	
	<!-- 엔터 공백을 모두 주석처리한다 -->
	<span class="child">1박스</span><!--
	--><span class="child">2박스</span>
	
	<!-- 가독성이 떨어진다 -->
</div>
```
2.  폰트 사이즈 조정
```css
.parent { font-size: 0px; }
.child { font-size: 1rem;}
```
3.  음수 margin 
```css
.child { margin-right: -4px; }
```

4.   float 속성 사용
 ```css
.child {
	float:left;
	padding: 10px 15px;
	border:1px solid #b7da8b;
	background:#f1ffdf;
}
```

5.  flex 속성 사용



<Br><br>
## calc() 함수
- 사칙연산으로 속성 값을 계산해주는 함수
-  +, - 에는 좌우 공백 필요
-  *, / 에는 좌우 공백 없어도 된다

 ```css
	width: calc(600px / 3); /* 200px */
	width: calc(100% / 3); /* 33.333333333…% */	
}
 ```