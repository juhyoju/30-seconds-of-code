
## Clearfix

```html
<div class="clearfix">
  <div class="floated">float a</div>
  <div class="floated">float b</div>
  <div class="floated">float c</div>
</div>
```
```css
.clearfix:after {
  content: '';
  display: block;
  clear: both;
}

.floated {
  float: left;
  padding: 4px;
}
```

## clearfix의 네 가지 방법
- 부모 요소 안의 자식 요소를 가로로 배치하게 될 때 (float) 부모 요소의 높이를 인식하지 못하는 오류를 해결하기 위한 방법

<br>

### 1. 가상 요소 `::after` 
- 부모 div에 가상 클래스 ::before, ::after를 사용하여 float 해제
```css
.clearfix:after { 
	 content:  '';
	 display: block; /* 또는 display:table 가능*/
	 clear: both; 
}
```

### 2. overflow 속성
- 부모 div에 `overflow:hidden` 또는 `overflow:auto` 사용  
- 부모 div가 자식 div를 담아낼 수 있도록 공간 확장
- 내용이 긴 콘텐츠가 부모요소를 벗어나서 보여져야 할 경우에 내용이 잘리거나 auto의 경우 스크롤바가 생김  
```css
.clearfix { overflow:hidden; }
```

### 3. clearfix 
- 의미없는 빈 태그 추가
```css
.clearfix:after { clear: both; height: 0; overflow: hidden; }  
```

### 4. 부모 요소에 float으로 대응
- `float`속성을 가진 자식요소의 부모요소에 똑같이 `float`를 적용

<br>

## ❗❗ 그러나
flexbox , grid layout을 사용하면 이 모든 것이 쉽게 한번에 해결된다.