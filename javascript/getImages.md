## getImages

요소 안에서 모든 이미지를 불러와서 배열로 반환하는 방법

```js
const getImages = (el, includeDuplicates = false) => {
  const images = [...el.getElementsByTagName('img')].map(img =>
    img.getAttribute('src')
  );
  return includeDuplicates ? images : [...new Set(images)];
};

// Examples
getImages(document, true); // ['image1.jpg', 'image2.png', 'image1.png', '...']
getImages(document, false); // ['image1.jpg', 'image2.png', '...']
```



### Element.getElementsByTagName()
특정 태그를 가진 모든 요소를 선택한다. 선택된 요소는 유사 배열 객체로 반환한다.

```js
document.getElementsByTagName( 'p' )[0];
element.getElementsByTagName( 'tagname' );
```


### Element.getAttribute()
해당 요소의 특정 속성을 반환한다. 만약 주어진 속성이 존재하지 않으면, null값이나 ""(빈 문자열)을 반환한다.


```js
element.getAttribute(attributeName); // attributeName : 값을 얻고자 하는 속성의 이름

// Example
var test = document.getElementById( 'test_id' ).getAttribute( 'title' );
// => id의 값이 text_id인 요소의 title 속성을 변수 test에 저장
```


### includeDuplicates
includeDuplicates가 `false` 이면 중복 항목을 제거

