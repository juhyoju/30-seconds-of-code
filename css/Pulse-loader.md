
## Pulse loader
애니메이션 지연 속성을 사용하여 로더 효과를 만들 수 있다.
```html
<div class="ripple-loader">
  <div></div>
  <div></div>
</div>
```
사이클의 두 지점에서 애니메이션을 정의할 것이기 때문에 자식 요소 div 두개

<br>

```css
.ripple-loader {
  position: relative;
  width: 64px;
  height: 64px;
}

.ripple-loader div {
  position: absolute;
  border: 4px solid #454ADE;
  border-radius: 50%;
  animation: ripple-loader 1s ease-out infinite;
}
```
부모 div를 크기 64 * 64 로 미리 정의한다.  
자식 div는 ripple-loader라는 이름의 애니메이션이 실행된다.


<br>

```css
.ripple-loader div:nth-child(2) {
  animation-delay: -0.5s;
}
```
첫번째 div에 1초동안 애니메이션이 발생하니까   
두번째 div에는 1초의 절반인 1.5초 딜레이가 발생하도록 설정하여 다른 시간에 애니메이션을 시작한다.


>느린 애니메이션 효과를 주려면 animation 시간을 변경하면 된다.  
delay 시간은  animation 시간의 절반

<br>

#### Keyframes

- 애니메이션 중간 과정에서 더 세밀하게 동작들을 제어할 수 있다. 
- 애니메이션과 animation-name속성에서 사용할 이름과 함께 생성한다.
- 최소한 0% 와 100% 같은 시간에 대한 규칙은 포함해야 한다. (%는 애니메이션의 시작과 끝 상태를 의미)
```css
@keyframes ripple-loader {
  0% {
    top: 32px;
    left: 32px;
    width: 0;
    height: 0;
    opacity: 1;
  }
  100% {
    top: 0;
    left: 0;
    width: 64px;
    height: 64px;
    opacity: 0;
  }
}
```
keyframe을 사용하여 사이클의 두 지점에서 애니메이션을 정의한다.
- 시작할 때 (0%) : 두 div는 가로 세로 없이 중앙에 위치한다.
- 끝날 때(100%) : 두 div는 가로 세로가 증가했고 투명도를 1 → 0으로 전환하여 사라지는 효과를 제공한다.
