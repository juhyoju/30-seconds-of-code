
## bottomVisible

  페이지 하단이 보여지는지 확인한다.

```javascript
const  bottomVisible = () =>
document.documentElement.clientHeight + window.scrollY >=
(document.documentElement.scrollHeight || document.documentElement.clientHeight);
```
```javascript
bottomVisible(); // true
```

  
## scrollY
- 문서가 수직으로 얼마나 스크롤됐는지 픽셀 단위로 반환한다.
- 문서가 위나 아래로 전혀 움직이지 않은 상태면 `0`을 반환한다.

  

```javascript
window.scrollY()
```

##### pageYOffset 속성은 scrollY의 다른 이름
```
window.pageYOffset === window.scrollY; // 항상 true`
```



## scrollHeight
- **`Element.scrollHeight`**  읽기 전용 속성
- 요소 콘텐츠의 총 높이를 나타내며, 바깥으로 넘쳐서 보이지 않는 콘텐츠도 포함한다.
- 수직 스크롤바를 사용하지 않고 요소의 콘텐츠를 모두 나타낼 때 필요한 최소 높이의 값과 동일하다.
- 요소의 콘텐츠를 수직 스크롤바 없이 모두 보여지는 경우 `scrollHeight`는 `clientHeight`와 동일하다.
```javascript
Element.scrollHeight()
```
- 눈에 보이지 않아도 요소에 들어있는 **컨텐츠의 전체 높이**
- **padding** 포함
- **margin, border, scrollbar** 제외
-  `::before`,  `::after` 등 의사 요소의 높이 포함


## clientHeight
```javascript
Element.clientHeight()
```
- 눈에 보이는 만큼의 **컨텐츠의 높이**
- **padding** 포함
- **margin, border, scrollbar** 제외
 

 ## offsetHeight
``` javascript
element.offsetHeight()
```
- offsetHeight는 요소의 높이
-  **padding, scrollbar, border** 포함
-  **margin** 제외
- css로 요소의 높이를 지정할 때 정해지는 높이값
-  `box-sizing` 속성에 따라 padding과 border 값이 제외될 수 있으므로 주의 필요
- 요소가 감춤 상태의 경우 offsetHeight는 0을 반환
