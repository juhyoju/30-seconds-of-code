
# border로 triangle 만들기
```html
<div class="triangle"></div>
```
```css
.triangle {
	width: 0; 
	height: 0; 
	border-top: 100px solid transparent;
    border-left: 100px solid transparent;
    border-right: 100px solid transparent;
    border-bottom: 100px solid blue;
}
```


## width, height 값이 0인 이유
- div 박스의 크기를 설정하게 되면, border의 두께만큼 중첩되어 영역이 확장되는 것이라 가운데 빈 공간이 생성된다.  
- div 박스의 width, height 값을 0으로 설정하면 빈 공간이 없이 상하좌우 딱지 모양으로  border 두께가 가득 채워지게 된다.  
- ~~하지만 이 문제는 box-sizing 으로 해결할 수 있다~~
<br>

## border로 ▲ 만들기
- **transparent** : 투명하게
```css
border-top: 100px solid transparent;
border-left: 100px solid transparent;
border-right: 100px solid transparent;
border-bottom: 100px solid blue;
```

- 100px짜리 border
-  하단의 테두리만 빼고 top, left, right의 border를 투명화
- bottom의 파란색 border만 보여지므로 **높이 100px짜리 파란색 ▲ 모양**이 만들어진다.

```css
border-top: 100px solid transparent;
border-left: 100px solid red;
border-right: 100px solid transparent;
border-bottom: 100px solid transparent;
```
- left border 제외한 나머지 border가 투명해지므로 빨간색 컬러의 ▶ 화살표 만들어진다.
<br>

## 가상요소(:before, :after) 로 말풍선 만들기

- 사각형(메세지 박스) + 삼각형
- **::before** : 요소의 콘텐츠 시작 부분에 생성된 콘텐츠 추가
- **::after** : 요소의 콘텐츠 끝 부분에 생성된 콘텐츠 추가
```html
<div class="box">박스 말풍선 만들기</div>
```
```css
/* box는 말풍선 몸통 */
.box {
	border:1px solid blue; 
	padding:15px; 
	position:relative; 
	background:white;
}

/* ::before 요소 사용, 삼각형의 보더 역할 */
.box::before {
	position:absolute;
	content:''; 
	border:11px solid transparent; 
	border-top-color:blue;
	top:100%;
	left:24px;
}

/* ::after 요소 사용, 삼각형의 몸통 역할 */
.box::after {
	position:absolute; 
	content:''; 
	border:10px solid transparent; 
	border-top-color:white;
	top:100%;
	left:25px;
}
```
- 삼각형의 몸통 백그라운드 = 말풍선 몸통 백그라운드 **[하얀색]**
- 삼각형 보더 몸통 컬러 = 말풍선 보더 컬러 **[파란색]**
- 삼각형 보더 몸통 크기 > 삼각형 몸통 크기
 (삼각형 몸통의 크기를 초과해야 삼각형 보더 역할이 가능)
 - 삼각형 몸통의 위치 = 삼각형 보더 몸통  **-1** 
  (크기가 큰 삼각형 보더 몸통의 중앙에 배치되어야 삼각형 몸통 전체에 보더 효과)