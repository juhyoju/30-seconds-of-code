## Typewriter effect

타이핑 효과 애니메이션

<br>

### animation-timing-function

애니메이션 움직임의 속도를 설정한다.

- 기본값 : `animation-timing-function : linear;`
- 문법 : `animation-timing-function : linear | ease | ease-in | ease-out | ease-in-out | step-start | step-end | steps(int,start|end) | cubic-bezier(n,n,n,n) | inherit;`

<br>

## 과정

1. 글자를 애니메이션화하는 `typing` 과 캐럿(텍스트 입력 커서)을 애니메이션화하는 `blink`로 두 개의 애니메이션을 정의한다.
2. 컨테이너 요소에 캐럿을 추가하기 위해 `:after` 를 사용한다.
3. JavaScript로 내부 요소의 텍스트를 세팅하고 문자 수를 포함하는 `--characters` 변수를 세팅한다. 이 변수는 텍스트를 애니메이션화하는 데에 사용된다.
4. 필요에 따라 내용을 보이지 않게 하기 위해 `white-space: nowrap` 와 `overflow: hidden` 를 적용한다.
