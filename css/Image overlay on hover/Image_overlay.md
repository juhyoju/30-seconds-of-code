## Image overlay on hover

마우스 오버하면 이미지 오버레이 효과 보여주기

<br>

### figcaption

- 부모 <figure> 요소가 포함하는 다른 콘텐츠에 대한 설명 혹은 범례를 나타낸다.

```html
<figure>
  <img src="/media/cc0-images/elephant-660-480.jpg" alt="Elephant at sunset" />
  <figcaption>An elephant at sunset</figcaption>
</figure>
```

## 과정

1. `:befoe`, `:after`을 사용하여 `top, bottom`을 세팅한다.
2. 원하는 효과를 내기 위해 불투명도, 변환 및 전환을 설정한다.
3. 오버레이 텍스트를 `<figcaption>`을 사용한다.
4. figcaption의 위치를 `flex:display; flex-direction:column; justify-content:center`로 세팅하여 이미지 중앙에 오도록 한다.
5. `:hover` 선택자로 모든 요소의 불투명도, 변환되는 것을 원하는 애니메이션 효과를 통해 보여준다.
