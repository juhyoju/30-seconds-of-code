## Custom Checkbox

상태 변경(체크) 시 애니메이션을 이용하여 스타일링하기

<br>

### SVG(Scalable Vector Graphics, 스케일러블 벡터 그래픽)

- 그래픽을 만들어내기 위한 XML-기반 언어(확장 가능한 벡터 그래픽)
- 움직이지 않는 이미지(static image)를 위해 사용할 수 있고, 애니메이션과 사용자 인터페이스를 위해서도 사용할 수도 있다.
- CSS 스타일 시트를 지원하여 그래픽에 사용되는 스타일을 그래픽의 내용물과 분리할 수 있다.
- 다른 문서 마크업 언어들과 함께 사용되는 스타일 시트들도 이미지가 요구되는 곳에 SVG 그래픽의 URL을 지정할 수 있다.  
  (예: HTML문서와 함께 사용하는 스타일 시트에서 `background` 속성값에 svg값의 url 지정 가능 )
- **장점** : 디자인 파일과 코드 동시 관리, 브라우저 호환성

### use

- 문서 전반에 걸쳐 요소를 재사용 할 수 있다.
- `x, y, width, height` 속성을 사용해 설정이 가능하다.
- 요소를 재사용함으로써 제작 시간을 아낄 수 있고, 코드를 최소화할 수 있다.

### 애니메이션 효과

1. **stroke-dasharray** : 윤곽선을 그리는 데에 사용되는 대시 및 간격의 패턴을 정의하는 속성
2. **stroke-dashoffset** : 관련된 stroke-dasharray이 어떤 지점에서부터 시작할지 정해주는 속성

```html
<svg class="checkbox-symbol">
  <symbol id="check" viewbox="0 0 12 10">
    <polyline
      points="1.5 6 4.5 9 10.5 1"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke-width="2"
    ></polyline>
  </symbol>
</svg>
```

<br>

## 과정

1. svg 요소를 이용하여 `체크 symbol` 생성한다.
2. 재사용이 가능한 svg 아이콘을 만들기 위해 `use 요소`를 삽입한다.
3. `checkbox-container` class를 만들고 flexbox를 사용하여 체크 박스의 적절한 레이아웃을 만든다.
4. input 요소는 숨기고 `label` 을 사용하여 체크 박스와 텍스트가 보이도록 한다.
5. `stroke-dashoffset` 사용하여 체크 기오에 애니메이션 효과를 준다.
6. `transform: scale(0.9)` css를 추가하여 줌 애니메이션 효과를 낸다.
