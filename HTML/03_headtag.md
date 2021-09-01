# HEAD 태그
> HTML 문서의 정보

## TITLE (웹 페이지의 제목)
HTML 문서의 제목을 정의한다. 웹 브라우저의 각 사이트 탭에서 이름으로 표시된다.

<img src="https://heropy.blog/images/screenshot/html-css-starter/browser_tabs.jpg" width="800" height="50"/>

```html
<head>
  <title>네이버</title>
</head>
```

## META DATA (웹 페이지의 정보)
웹페이지에 관한 정보(표시 방식, 제작자, 내용, 키워드 등)를 검색엔진이나 브라우저에 제공한다. 빈(Empty) 태그이다.

```html
<head>
  <meta charset="UTF-8">
  <meta name="author" content="박지원">
  <meta name="description" content="내 사이트">
</head>

<문서의정보범위>
  <정보 문자인코딩방식="UTF-8">
  <정보 정보종류="사이트제작자" 정보값="박지원">
  <정보 정보종류="사이트설명" 정보값="내 사이트">
</문서의정보범위>
```

| 속성 | 의미 |	값 |
|------|------|----|
| charset |	문자인코딩 방식 (텍스트가 출력되는 방식) |	UTF-8, EUC-KR 등 |
| name | 검색엔진 등에 제공하기 위한 정보의 종류(메타 데이터)	| author, description, keywords, viewport 등 |
| content |	name 이나 http-equiv 속성의 값을 제공 |	

**UTF-8**은 아시아권 언어에 특화된 문자인코딩 방식이다.

## LINK (CSS 불러오기)
외부 문서, 특히 CSS 문서를 불러와 연결할 때 사용, 빈 태그이다.

```html
<head>
  <link rel="stylesheet" href="./css/main.css">
  <link rel="icon" href="./favicon.png">
</head>

<문서의정보범위>
  <외부문서연결 관계="CSS" 문서경로="./css/main.css">
  <외부문서연결 관계="사이트대표아이콘" 문서경로="./favicon.png">
</문서의정보범위>
```

| 속성 | 의미 |	값 |
|----|----|---|
| rel |	(필수)현재 문서와 외부 문서와의 관계를 지정 |	stylesheet, icon 등 |
| href |	외부 문서의 위치를 지정 |	경로 |

> rel = relationship (관계) , href = hyperlink (하이퍼링크)

## STYLE (CSS 작성하기)

CSS를 HTML 문서 내부에 작성할 때 `<head>`태그 안에 `<style>`태그를 작성한다.

```html
<style>
  img {
    width: 100px;
    height: 200px;
  }
  p {
    font-size: 20px;
    font-weight: bold;
  }
</style>

<스타일정의>
  <!-- CSS 코드 -->
</스타일정의>
```

## SCRIPT (JS 불러오거나 작성하기)
Java Script는 CSS처럼 `<style></style>`로 작성하거나 `<link>`로 불러오지 않는다.
`<script></script>` 태그 하나로 두 가지 방법을 모두 할 수 있다.

```html
<!-- 불러오기 -->
<script src="./js/main.js"></script>

<!-- 작성하기 -->
<script>
  function windowOnClickHandler(event) {
    console.log(event);
  }
  window.addEventListener('click', windowOnClickHandler);
</script>

<!-- 불러오기 -->
<자바스크립트 문서경로="./js/main.js"></자바스크립트>

<!-- 작성하기 -->
<자바스크립트>
  <!-- JS 코드 -->
</자바스크립트>
```
