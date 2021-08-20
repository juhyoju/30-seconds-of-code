## Menu on image hover

이미지에 마우스 오버하면 메뉴가 오버레이 되도록 하기

<br>

### figure

`<figure>` 요소는 독립적인 콘텐츠를 표현하며 `<figcaption>` 요소로 부연 설명을 할 수 있다.

```html
<figure class="hover-menu">
  <img src="https://picsum.photos/id/1060/800/480.jpg" />
</figure>
```

<br>

## 과정

1. `<img>` 요소를 덮기 위해 `<figure>` 요소를 사용한다.
2. 메뉴 링크를 포함하는 `<div>` 요소를 만든다.
3. `opacity`와 절대 위치값 `position:absolute`, `right` 특성을 이용하여 마우스 오버 시 보여지도록 한다.
4. 애니메이션(슬라이드) 효과를 위해 `transition` 스타일을 적용한다.
5. `div` (메뉴 박스)의 절대 위치값 `left` 특성을 div의 `width`의 음수로 설정한다.
6. 이미지에 마우스 오버 시 메뉴가 슬라이드 애니메이션이 보여지도록 `div`의 `left` 특성을 `0`으로 재설정한다.
7. 메뉴 항목을 수직 정렬하기 위해 `display:flex`를 사용한다.

### 결과
![image](https://user-images.githubusercontent.com/47467774/130174146-17b9d2ed-37a2-4cdd-a5d1-0726c0164637.png)     ![image](https://user-images.githubusercontent.com/47467774/130174165-c5afe2df-3112-438b-b766-bc7864032206.png)


