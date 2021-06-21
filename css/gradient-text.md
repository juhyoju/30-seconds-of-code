
## Gradient text

**텍스트에 그라데이션 효과**를 적용하는 방법  
❗ 웹킷 계열에서 간단히 적용 가능   
❗❗ 표준 아님
```css
h1 {
	background: linear-gradient(to right top, #70D6FF, #e91e63);
	-webkit-text-fill-color: transparent;
	-webkit-background-clip: text;
}
```

## background : linear-gradient
텍스트 요소에 그라데이션 배경을 제공한다.  

`linear-gradient( direction, color1, color2, …, color3 );`
 

####  예시
```css
background : linear-gradient(45deg, blue, red);
background : linear-gradient(to left top, blue, red);
background : linear-gradient(to right, yellow 50%, red, purple, blue);
```


## -webkit-background-clip

#### 속성값
- **border-box** : [초기값] 배경이 테두리의 바깥 경계까지 차지한다. (Z축 순서 상 테두리 아래 위치)
- **padding-box** : 배경이 안쪽 여백의 바깥 경계까지 차지하며, 테두리 밑에는 배경을 그리지 않는다.
- **content-box** : 배경을 콘텐츠 상자에 맞춰 그린다.
- **text** : 배경을 텍스트로 클리핑하고 그라데이션 배경을 색상으로 채운다.

## -webkit-text-fill-color : transparent;
텍스트를 투명하게 채운다.