## Reset all styles
```html
<h1>h1 타이틀</h1>
<h2>h2 타이틀</h2>
<div>div 박스</div>
<hr>
<ul>
	<li>리스트 1</li>
	<li>리스트 2</li>
	<li>리스트 3</li>
	<li>리스트 4</li>
</ul>
```

#### 기본 스타일
![image](https://user-images.githubusercontent.com/47467774/122167890-8b37ed00-ceb6-11eb-9868-468429b2417c.png)

<br>


## all 속성
브라우저마다 가지고 있는 기본값이 다르기 때문에 unicode-bidi (en-US), direction (en-US), CSS 사용자 지정 속성을 제외한 모든 속성을 초기화한다.  
**주의** : 어느것도 unicode-bidi (en-US)와 direction (en-US) 속성에는 영향을 주지 않는다.


- **initial** : 요소의 모든 속성을 **초기값** 으로 변경
- **inherit**  : 요소의 모든 속성을 **상속값** 으로 변경
- **unset** : 요소의 모든 속성을, 속성이 값을 상속하는 경우 상속값으로, 아니면 초깃값으로 변경

<br>

## 결과
```css
h1, h2, div, hr, ul, li { all:unset; }
```

![image](https://user-images.githubusercontent.com/47467774/122167945-9c80f980-ceb6-11eb-8eb5-20daa55b505d.png)
