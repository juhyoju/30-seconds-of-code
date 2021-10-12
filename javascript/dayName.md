## dayName

날짜 객체에서 요일의 이름을 가져오는 방법

1. `Date.prototype.toLocaleDateString()`을 `{weekday : 'long'}` 옵션과 사용한다.
2. 두 번째 인수에 특정 언어로 가져오도록 설정하거나 기본 locale을 사용할 경우 생략한다.

### 기본 형식

```js
date.toLocaleDateString([locale[, options]])
```

#### locale (선택)

생략하면 웹브라우저의 기본 locale 값을 사용하지만 직접 변경할 수도 있다.

#### options

아래 속성들을 일부 포함한 객체로 지정할 수 있다.

- **dateStyle** : 날짜 형식 스타일 ( full / long / medium / short )
- **timeStyle** : 시간 형식 스타일 ( full / long / medius / short )

```js
const dayName = (date, locale) =>
  date.toLocaleDateString(locale, { weekday: "long" });

/* Example */
dayName(new Date()); // 'Saturday'
dayName(new Date("09/23/2020"), "ko-KR"); // '토요일'
```
