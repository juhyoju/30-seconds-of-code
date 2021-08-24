## renderElement

### 지정된 DOM 요소에서 주어진 DOM 트리(엘리먼트)를 렌더링하기

1. 주어진 요소가 텍스트 요소인지 확인하려면 `type`을 사용하여 첫 번째 인수를 `type`과 `props`로 분해한다.
2. 요소의 `type`을 기준으로 `Document.createTextNode()` 또는 `Document.createElement()`를 사용하여 DOM요소를 생성한다.
3. 필요에 의해 `Object.keys()`를 사용하여 DOM 요소에 특성을 추가하고 이벤트 수신기를 세팅한다.
4. `재귀`가 있는 경우 `props.children`을 렌더링한다.
5. `Node.appendChild()`를 사용하여 특정 `container`에 DOM요소를 추가한다.

```js
const renderElement = ({ type, props = {} }, container) => {
  const isTextElement = !type;
  const element = isTextElement ? document.createTextNode('') : document.createElement(type);

  const isListener = (p) => p.startsWith('on');
  const isAttribute = (p) => !isListener(p) && p !== 'children';

  Object.keys(props).forEach((p) => {
    if (isAttribute(p)) element[p] = props[p];
    if (!isTextElement && isListener(p)) element.addEventListener(p.toLowerCase().slice(2), props[p]);
  });

  if (!isTextElement && props.children && props.children.length)
    props.children.forEach((childElement) => renderElement(childElement, element));

  container.appendChild(element);
};

/* Example */
const myElement = {
  type: 'button',
  props: {
    type: 'button',
    className: 'btn',
    onClick: () => alert('Clicked'),
    children: [{ props: { nodeValue: 'Click me' } }],
  },
};

renderElement(myElement, document.body);
```

<br>

### Document.createTextNode()

텍스트 노드를 추가하는 것
`텍스트 = document.createTextNode(데이터);`

- **텍스트** : 생성된 텍스트 노드
- **데이터** : 텍스트 노드에 쓰여지는 문자열

### Document.createElement()

HTML 문서에서, 지정한 `tagName`의 HTML 요소를 만들어서 반환한다.  
tagName을 인식할 수 없으면 `HTMLUnKnownElement`를 대신 반환한다.

```html
<body>
  <div id="div1">위의 텍스트는 동적으로 추가했습니다.</div>
</body>
```

```js
document.body.onload = addElement;

function addElement() {
  // create a new div element
  var newDiv = document.createElement('div');
  // and give it some content
  var newContent = document.createTextNode('환영합니다!');
  // add the text node to the newly created div
  newDiv.appendChild(newContent);

  // add the newly created element and its content into the DOM
  var currentDiv = document.getElementById('div1');
  document.body.insertBefore(newDiv, currentDiv);
}
```

##### 결과

환영합니다!  
위의 텍스트는 동적으로 추가했습니다.

### Node.appendChild()

한 노드를 특정 부모 노드의 자식 노드 리스트 중 마지막 자식으로 추가하는 것  
만약, 주어진 노드가 이미 document에 존재하는 노드를 참조하고 있다면 appendChild() 메소드는 노드를 현재 위치에서 새로운 위치로 이동시킨다. (**한 노드가 document 상 두 지점에 동시 존재할 수 없음**)

```js
// 새로운 단락 요소를 생성하고 문서에 있는 바디 요소의 끝에 붙인다.
var p = document.createElement('p');
document.body.appendChild(p);
```
