## Flexbox centering
Flexbox를 사용하여 부모 요소 내에서 자식 요소를 수평 및 수직으로 중앙 배치할 수 있다.

```html
<div class="parent_box">
	<div class="child_box">Centered content</div>
</div>
```
```css
.parent_box {
  display: flex;
  justify-content: center;
  align-items: center;
  background:#eee;
  height:200px;
}
.child_box { /*가정*/
    width: 100px;
    height: 100px;
    background: #fff;
    text-align: center;
}   
```

## flex 속성
- 하나의 플렉스 아이템(자식 요소)이 자신의 컨테이너(부모 요소)가 차지하는 공간에 맞추기 위해 크기를 키우거나 줄이는 방법을 설정하는 속성
- 블록 레이아웃, 인라인 레이아웃, 테이블 레이아웃 및 위치 지정 레이아웃 모드와 더불어 CSS3에서는 보다 복잡한 블록 타입 레이아웃 모드인 flexbox 레이아웃을 지원한다. 
- flexbox의 콘텐츠는 어떤 방향에든 위치할 수 있으며, 동적으로 변경가능한 순서를 지정할 수도 있고, 가용한 공간 내에서 크기와 위치를 자동으로 조정하기도 한다.  
- flex-grow, flex-shrink, flex-basis의 축약속성
  
  <br>

## 수평 중앙 배치

- `child_box` 를 수평으로 중앙 정렬을 하려고 할 때, 부모 `parent_box` 에 속성을 적용하면 된다.  
- `display: flex;`. `justify-content: center`  
- `justify-content` 는 **X축(수평)** 속성이다.

```css
.parent_horizontal {
	display : flex;
	justify-content : center;	
	background : pink;
	height : 200px;
}
```


## 수직 중앙 배치

- `child_box` 를 수평으로 중앙 정렬을 하려고 할 때, 부모 `parent_box` 에 속성을 적용하면 된다.  
- `display: flex;`. `align-items: center` 
- `align-items` 은 **Y축(수직)** 속성이다.
- 부모 요소에 높이값으 설정되어 있지 않으면, 정렬되지 않을 수 있다.

```css
.parent_vertical {
	display : flex;
	align-items : center;
	background : skyblue;
	height : 200px;
}
```

## 수평 수직 중앙 배치

- 부모 `parent_box` 에 X축 속성(justify-content)과 Y축 속성(align-items) 모두를 적용하면 자식 `child_box`는 가로 세로 중앙에 배치된다.

```css
.parent_center {
  display: flex;
  justify-content: center;
  align-items: center;
  background:#eee;
  height:200px;
}
```