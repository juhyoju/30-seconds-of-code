## Bouncing loader

바운싱 로더 애니메이션 효과

<br>

### transform: translate 3d()

3D 공간에서 요소를 재배치한다.

`translate3d(tx, ty, tz)`

- `tx` : 가로 좌표 (숫자 또는 백분율)
- `ty` : 세로 좌표 (숫자 또는 백분율)
- `tz` : z 좌표 (숫자)

<br>

### animation-direction: alternate

애니메이션이 앞으로, 뒤로, 또는 앞뒤로 번걸아 재생되어야 하는지 여부를 지정

```css
/* Single animation */
animation-direction: normal;
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;

/* Multiple animations */
animation-direction: normal, reverse;
animation-direction: alternate, reverse, normal;

/* Global values */
animation-direction: inherit;
animation-direction: initial;
animation-direction: unset;
```

- `animation-direction: normal;` : 매 사이클마다 정방향으로 재생 (기본값)
- `animation-direction: reverse;` : 역방향으로 재생. 즉, 애니메이션 단계가 거꾸로 수행되고 타이밍 기능 또한 반대로 재생
- ``animation-direction: alternate;` : 매 사이클마다 각 주기의 방향을 뒤집으며 첫 번째 반복은 정방향으로 진행한다. 사이클이 짝수/홀수인지 결정하는 카운트에서 하나가 시작된다.

<br>

## 과정

1. `@keyframes`를 이용하여 요소의 투명도를 변경하는 애니메이션과 `transform: translate 3d()`를 이용한 2D 평면에서 변형하는 애니메이션인 두 가지 `state`를 정의한다.
2. 애니메이션 성능 향상을 위해 `transform: translate3d()`을 위해 단일 축 변형을 이용한다.
3. 튕겨지는 원을 위한 부모 컨테이너 `.bouncing-loader`를 생성한다.
4. .bouncing-loader를 `display: flex` 와 `justify-content: center` 로 중앙 배치한다.
5. 튕겨오르는 원인 `<div>` 요소를 너비와 높이를 16px로 적용하고 `border-radius:50%`로 원형으로 만든다.
6. 세 개의 원에 각각에 `bouncing-loader` 애니메이션을 적용한다.
7. 각각 다른 `animation-delay`와 `animation-direction: alternate`를 사용하여 적절한 효과를 만든다.
