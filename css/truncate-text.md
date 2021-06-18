
## Truncate text
```html
 <p>가나다라마바사아자차카타파하가나다라마바사아자차카타파하가나다라마바사아자차카타파하가나다라마바사아자차카타파하가나다라마바사아자차카타파하</p>
```


## 말줄임표
```css
p {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  width: 200px;
  display:block;
}
```
❗❗ Only works for single line elements.
(한 줄로만 말줄임표가 가능하다)

#### text-overflow
글자가 지정한 너비를 초과할 경우, 어떻게 처리할지 선택하는 속성
-   `clip` : 기본값
-   `ellipsis` : 말줄임표로 처리 (상위요소의 너비가 auto로 되어있는 경우는 적용 불가)
-   `inherit` : 상위 요소의 속성과 동일하게 적용

#### white-space
요소 안에서 공백은 어떤식으로 처리할 것인지를 선택하는 속성 (줄바꿈(line-break), 들여쓰기(tab), 공백(space))
- `normal` : 기본값 (공백을 여러개 넣어도 공백을 1개로 처리)
- `nowrap` : 공백을 여러개 넣어도 1개로 처리 (텍스트가 길어져도 줄바꿈을 하지않고 1줄로 표시)
- `pre` : 공백을 코드에 있는 그대로 표시 (코드에 줄바꿈이 없으면 줄바꿈을 실행하지 않음)
- `pre-wrap` : 공백을 코드에 있는 그대로 표시 (코드에 줄바꿈이 없어도 자동으로 줄바꿈을 실행)
- `pre-line` : 공백을 여러개 넣어도 1개로 처리 (코드에 줄바꿈이 없어도 자동으로 줄바꿈을 실행하며 코드에 줄바꿈이 있을 때도 그대로 실행)

#### 결과
![image](https://user-images.githubusercontent.com/47467774/122534093-28cd2100-d05d-11eb-8a8f-bb797a236e58.png)


<br>

## 두 줄 이상일 경우
```css
p {
  width: 300px;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  
  /* 3줄까지 출력 */
  -webkit-line-clamp: 3;
  line-height: 1.2em;
  height: 3.6em; 
}
```

#### -webkit-line-clamp
✅ webkit 엔진을 사용하지 않는 브라우저를 위한 속성  
line-height 속성과 height 속성을 이용하여 높이를 계산하여 적용  (height = line-height * 줄수)

#### 결과
![image](https://user-images.githubusercontent.com/47467774/122534128-31bdf280-d05d-11eb-9a6d-eb62b7680c09.png)


