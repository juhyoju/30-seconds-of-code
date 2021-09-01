## Responsive image mosaic

반응형 이미지 모자이크 만드는 방법

<br>

### display:grid

- 그리드는 수평선과 수직선이 교차해서 이루어진 집합체(열과 행을 정의)
- 페이지를 여러 주요 영역으로 나누거나 크기와 위치 등을 테이블과 달리 다양한 레이아웃을 훨씬 더 쉽게 구현할 수 있다.
- 부모요소 : Grid Container (그리드 컨테이너)
- 자식요소 : Grid Item (그리드 아이템)

<br>

### grid-template

컨테이너에 그리드 트랙의 크기를 지정해주는 속성

- `grid-template-column` : 열(column)의 배치
- `grid-template-rows` : 행(row)의 배치

#### 예

```css
grid-template-columns: 200px 200px 500px; // column을 200px 200px 500px 로 세조각으로 나눔
grid-template-columns: 1fr 1fr 1fr; // 숫자 비율대로 크기를 나눔 (1:1:1 비율로 3 column)
```

<br>

### grid-row / grid-column : span ?

위치를 정해주지 않고 상대적으로 자식 그리드의 크기만 설정할 때

```css
grid-column: span 2; // 가로로 두 그리드 차지
grid-row: span 2; // 세로로 두 그리드 차지
```

> ⚠ Internet Explorer 지원하지 않음

<br>

## 과정

1. 반응형 레이아웃을 만들기 위해 `display:grid` 를 사용한다.
2. `grid-row: span 2 / auto` 와 `grid-column: span 2 / auto`를 이용하여 각각 2행 또는 2열에 걸치도록 아이템을 만든다.
3. 작은 크기의 화면에서는 적용되지 않도록 `미디어쿼리`로 이전 스타일을 감싼다.
