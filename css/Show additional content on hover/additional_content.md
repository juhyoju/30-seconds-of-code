## Show additional content on hover

마우스 오버 시 부가 설명이 보여지는 카드를 만드는 방법

<br>

### :focus-within

`element:focus-within { color: red; }`

- 포커스를 받았거나, 포커스를 받은 요소를 포함하는 요소를 나타낸다.
- 부모 요소에 사용하면 내부 자식 요소에 포커스 된 경우까지 스타일이 적용된다.

> ⚠ Internet Explorer 지원하지 않음

<br>

## 과정

1. 수직으로 오버플로우되는 요소를 숨기기 위해 카드에 `overflow:hidden` 적용
2. `:hover`와 `:focus-within` 선택자를 사용하여 카드에 마우스 오버되거나 포커스할 경우 카드의 스타일을 변경한다.
3. 마우스 오버 / 포커스에 전환 효과를 적용하기 위해 `transition:0.3s all ease`를 설정한다.

### 결과
