
## Circle
```html
<div class="circle"></div>
```
```css
.circle {
  border-radius: 50%;
  width: 32px;
  height: 32px;
  background: #9C27B0;
}
```

## border-radius
- 요소 테두리를 둥글게 만드는 속성
- 속성의 값에는 px, % 등 길이 단위로 입력
- top-left / top-right / bottom-right / bottom-left 순서

#### 예제1
```html
 <div class="border10">border-radius:10px;</div>
 <div class="border25">border-radius:25%;</div>
```
```css
.border10 {
	border:5px solid red;
	border-radius:10px;
 }
 .border25 {
	border:5px solid blue;
	border-radius:25%;
 }
```
- 각 div 박스의 테두리가 10px, 25% 씩 둥글게 적용된다.  

![image](https://user-images.githubusercontent.com/47467774/117663325-84dd9380-b1db-11eb-9267-7f8aa067ad30.png)


<br>

#### 예제2
```html
 <div class="border">border-radius:25px 100px 10px 50px;</div>
 <div class="borderSame">border-radius:50p 0;</div>
```
```css
.border {
	border:5px solid green;
	border-radius:25px 100px 10px 50px;
 }
 .borderSame {
	border:5px solid pink;
	border-radius:50px 0;
 }
```
- border박스 : 왼쪽 위 25px, 오른쪽 위 100px, 오른쪽 아래 10px, 왼쪽 아래 50px 만큼 둘글게 적용된다.
- borderSame 박스 : 왼쪽 위 / 오른쪽 아래 50px, 오른쪽 위 / 왼쪽 아래 0   

![image](https://user-images.githubusercontent.com/47467774/117663484-ab033380-b1db-11eb-8b55-167bc643a5e7.png)


<br>

#### 예제3
```html
<div class="borderCircle">border-radius:50%;</div>
```
```css
.borderCircle {
	border:5px solid black;
	border-radius:50%;
 }
```
- 상하좌우 같은 값의 둥글기가 적용되므로 원형이 완성된다.  

![image](https://user-images.githubusercontent.com/47467774/117663540-b9e9e600-b1db-11eb-8ad1-72448f298199.png)
