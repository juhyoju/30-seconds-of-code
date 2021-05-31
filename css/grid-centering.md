## Grid centering

Grid 를 사용하여 부모 요소 내에서 자식 요소를 수평 및 수직으로 중앙 배치할 수 있다.

```html
<div class="parent_box">
	<div class="child_box">Centered content</div>
</div>
```
```css
.parent_box {
	display: grid;	
	justify-content: center;
	align-items: center;
	background: #eee;
	height: 200px;
}
.child_box {
	width: 100px;
	height: 100px;
	background: #fff;
	text-align: center;
}
```

## grid 속성
- 행과 열로 구성한다.
- 다양한 레이아웃을 간결하게 구현할 수 있도록 많은 기능을 제공한다.
- 컨테이너가 될 부모 요소에게 grid를 적용하면 자식 요소들은 grid Items 이다.
- 그리드 레이아웃으로 작업 할 때 블록 축과 인라인 축 에 대해 두 개의 축을 정렬 할 수 있다.
- 세로 열과 가로 행을 기준으로 요소를 정렬하여 구성할 수 있다.

<br>

## 수평 중앙 배치

-  `child_box` 를 수평으로 중앙 정렬을 하려고 할 때, 부모 `parent_box` 에 속성을 적용하면 된다.
-  `display: grid;`,  `justify-content: center`
-  `justify-content` 는 **X축(수평)** 속성이다.

```css
.parent_horizontal {
	display : flex;
	justify-content : center;
	background : pink;
	height : 200px;
}
``` 

![image](https://user-images.githubusercontent.com/47467774/119782445-2c123880-bf07-11eb-8f53-d6e0c337260e.png)



## 수직 중앙 배치

-  `child_box` 를 수평으로 중앙 정렬을 하려고 할 때, 부모 `parent_box` 에 속성을 적용하면 된다.
-  `display: grid;`,  `align-items: center`
-  `align-items` 은 **Y축(수직)** 속성이다.

  
```css
.parent_vertical {
	display : grid;
	align-items : center;
	background : skyblue;
	height : 200px;
}
```

![image](https://user-images.githubusercontent.com/47467774/119782475-35030a00-bf07-11eb-9a66-e210b6f45266.png)


## 수평 수직 중앙 배치

- 부모 `parent_box` 에 X축 속성(justify-content)과 Y축 속성(align-items) 모두를 적용하면 자식 `child_box`는 가로 세로 중앙에 배치된다.
- **Grid** 에서는 `align-items` 속성과 `justify-content` 속성을 한 번에 적용할 수 있는 `place-items` 속성을 제공한다. 그래서 `place-items` 속성만 center로 설정하면 가로 세로 중앙 정렬 가능하다.
  

```css
.parent_center {
	display: grid;
	/* justify-content: center;
	align-items: center; */
	place-items: center;
	background:#eee;
	height:200px;
}
``` 

![image](https://user-images.githubusercontent.com/47467774/119782520-3fbd9f00-bf07-11eb-845a-0fb226df9f58.png)


<br>

## Flex와 Grid 의 차이

### Flex
- 1차원으로 수평, 수직 영역 중 하나의 방향으로만 레이아웃을 나눌 수 있따.
- 컨텐츠 중심

### Grid
- Grid는 2차원으로 수평 수직을 동시에 영역을 나눌 수 있다.
- 레이아웃 중심