## Mouse cursor gradient tracking

마우스 커서를 따라 그라데이션이 따라다니는 호버 효과

### 사용자 지정 속성 (CSS 변수, 종속 변수)

1. CSS 저작자가 정의하는 개체로, 문서 전반적으로 재사용할 임의의 값을 담는다.
2. 사용자 지정 속성은 전용 표기법을 사용해 정의한다. 예: `(--main-color: black;)`
3. var() 함수를 사용해 접근한다. 예: `(color: var(--main-color);)`
4. 사용자 지정 속성의 이름은 대소문자를 구분한다.

**✅ 장점**

- 한 영역에 값을 저장해놓고 다른 여러 곳에서 참조할 수 있다. (반복적인 값을 한번에 수정할 수 있다. )
- 의미를 가지는 식별자를 사용함으로써 코드 이해가 쉽다. (예: #00ff00 보다 --main-text-color 가 이해가 쉽다.)

#### 선언

```css
:root {
  --main-bg-color: brown;
}
```

#### 참조

```css
element {
  background-color: var(--main-bg-color);
}
```

> ⚠ Internet Explorer 지원하지 않음

<br>

### 원형 그라데이션 (background: radial-gradient: ...)

`radial-gradient( shape size at position, color1, color2, ..., color3 )`

- shape : 원(circle) / 타원(ellipse, 기본값)
- size : 크기 (closest-side , closest-coner, farthest-side , farthest-corner)
- position : 시작 위치 (left,right,center,bottom / %)
- color : 색상

<br>

### Document.querySelector()

특정 선택자 또는 선택자 그룹에서 일치하는 문서 내 `첫번째 element` 반환하고,  
일치하는 element가 없으면 `null` 반환

<br>

### EventTarget.addEventListener()

- `EventTarget` 의 `addEventListener()` 메서드는 지정한 이벤트가 대상에 전달될 때마다 호출할 함수를 설정한다.
- 일반적인 대상은 `Element, Document, Window`지만, XMLHttpRequest와 같이 이벤트를 지원하는 모든 객체를 대상으로 지정할 수 있다.

> `addEventListener()` 는 EventTarget의 주어진 이벤트 유형에, EventListener를 구현한 함수 또는 객체를 이벤트 처리기 목록에 추가해 작동한다.

<br>

### mousemove 이벤트

- 사용자가 해당 element에서 마우스를 움직였을 때 발생한다.
- 마우스가 1px 이라도 움직이게 되면 발생해서 UI를 느리게 하기 때문에 꼭 필요한 경우에만 사용하는 것이 좋다.

<br>

### Element.getBoundingClientRect()

- 요소의 크기와 뷰포트에 상대적인 위치에 대한 정보를 제공하는 DOMRect 개체를 반환한다.
- 반환된 값은 padding, border 를 포함한 전체 요소를 포함하는 가장 작은 직사각형인 DOMRect 개체이다.
- `left, top, right, bottom, x, y, width, height` 속성은 전체 직사각형의 위치와 크기를 px 단위로 설명한다.
- **width와 height를 제외한 나머지 속성은 뷰포트(viewport)의 top-left를 기준으로 하며, viewport를 기준으로 하는 상대적인 값이기 때문에 `scroll`로 인해 위치가 변경될 때마다 값이 변경된다.**

`domRect = element.getBoundingClientRect();`

<br>

### CSSStyleDeclaration.setProperty()

css 스타일 선언 객체의 속성에 대해 새 값을 설정한다.

`style.setProperty(propertyName, value, priority);`

- propertyName : 수정할 CSS 속성 이름을 나타내는 DOM 문자열
- value : 새 속성을 포함하는 DOM 문자열로 지정하지 않으면 빈 문자열로 처리된다.
  (❗ !important 포함되면 안됨 - 우선순위 매개변수를 사용하여 설정해야 한다.)
- priority : 중요한 우선순위를 설정할 수 있고 지정하지 않으면 빈 문자열로 처리된다.

```js
style.cssPropertyName = "value";
```

> JavaScript는 스타일 선언 객체에 CSS 속성을 설정할 수 있는 간단한 구문을 제공한다.

<br>

## 과정

1. 버튼에서 마우스 위치를 추적하는 데에 사용되는 css 변수 `--x`, `--y` 를 선언한다.
2. 그라데이션 면적을 수정하는 데에 사용되는 css 변수 `--size`를 선언한다.
3. `background: radial-gradient(circle closest-side, pink, transparent);` 를 이용하여 적절한 위치에 그라데이션을 만든다.
4. `Document.querySelector()` 와 `EventTarget.addEventListener()` 를 이용하여 `mousemove` 이벤트 처리기를 등록한다.
5. `Element.getBoundingClientRect()` 와 `CSSStyleDeclaration.setProperty()` 를 이용하여 `--x`, `--y`의 css 변수의 값을 바꿔준다.
