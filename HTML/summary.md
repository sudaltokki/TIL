# HTML 개요  
> 패스트캠퍼스 강의를 듣고 학습한 내용을 기록합니다.  
> 참고한 블로그 [heropy.blog](https://heropy.blog/2019/04/24/html-css-starter/)

## HTML (Hypertext Markup Language)
* 웹 문서를 만들기 위하여 사용하는 기본적인 웹 언어의 한 종류
* 웹의 튼튼한 구조를 만들기 위한 정적 언어

## 기본형태
태그는 각자의 의미를 가지고 있으며 다음과 같은 형태를 가집니다.

```html
<TAG></TAG>
<TAG>CONTENT</TAG>
```

```html
<h1>위대한 개츠비</h1>
<p>지금보다 어리고 쉽게 상처받던 시절 아버지는 ...</p>

<주제1>위대한 개츠비</주제1>
<문단>지금보다 어리고 쉽게 상처받던 시절 아버지는 ...</문단>
```

태그는 열리고(open) 닫히는(close) 태그 구조가 한 쌍 (start, end 라고도 말한다.)  

닫히는 태그는 태그 이름 앞에 `/`(슬래시)가 붙는다. 

이 구조는 태그의 범위를 만들어 준다.

## 속성(Attributes)과 값(Value)
태그의 기능을 확장하기 위해 사용한다.

```html
<TAG 속성="값"></TAG>
```

```html
<img src="./my_photo.jpg" alt="내 프로필 사진" />
<div class="name">박지원</div>

<이미지삽입 소스위치="./my_photo.jpg" 대체텍스트="내 프로필 사진" />
<의미없는분할 태그별명="name">박지원</의미없는분할>
```

`<img />`는 이미지를 삽입할 때 사용하는 태그이다.  

`src(source)`라는 속성을 사용해서 삽입할 이미지의 경로를 지정하고,    

`alt(alternative)`라는 속성을 사용해서 이미지를 출력하지 못하는 상황에 이미지 대신 보여질 텍스트를 지정한다.    

`<div></div>`는 의미를 가지지 않는 분할 태그이고, `class`는 태그의 별명이다.  

## 부모와 자식 요소
태그 A가 태그 B의 콘텐츠로 사용되면, 태그 B는 태그 A의 부모 요소, 태그 A는 태그 B의 자식 요소라고 한다.

```html
<PARENT>
  <CHILD></CHILD>
</PARENT>
```

```html
<section class="animals">
  <h1>동물 목록</h1>
  <ul>
    <li>수달</li>
    <li>토끼</li>
  </ul>
</section>

<!-- 다음과 같이 이해할 수 있습니다. -->
<섹션영역 태그별명="animals">
  <주제1>동물 목록</주제1>
  <순서없는목록>
    <항목>수달</항목>
    <항목>토끼</항목>
  </순서없는목록>
</섹션영역>

```

`<section></section>` 안에는 콘텐츠 `<h1></h1>`, `<ul></ul>`, `<li></li>`가 있고 `<ul></ul>` 안에는 콘텐츠 `<li></li>`가 있다.

이 때 `<section>`는 `<h1>`과 `<ul>`의 부모 요소이고, `<ul>`은 `<li>`의 부모 요소이다. 

반대로 `<h1>`과 `<ul>`은 `<section>`의 자식 요소이고, `<li>`는 `<ul>`의 자식 요소이다.

## 빈 태그
닫히는 개념이 없는 태그

```html
<!-- `/`가 없는 빈 태그 -->
<TAG>

<!-- `/`가 있는 빈 태그 -->
<TAG/>
<TAG />
```

HTML5에서는 위 2가지 형태를 다 사용할 수 있는데, XHTML 버전이나 개발 환경에 따라 `/`를 사용하는 것이 필수가 될 수 있다.

빈 태그들은 범위가 존재하지 않고, 대부분 속성과 값의 형태가 빈 태그 안에 포함된다.

## HTML 문서의 범위

```html
<!DOCTYPE html>
<html>
  <head>
    문서의 정보
  </head>
  <body>
    문서의 구조
  </body>
</html>
```

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="author" content="박지원">
    <meta name="description" content="내 사이트가 최고!">
    <title>내 사이트</title>
    <link rel="stylesheet" href="./css/main.css">
    <script src="./js/main.js"></script>
</head>
<body>
    <section>
      <h1></h1>
      <div>
        <ul>
          <li></li>
          <li></li>
        </ul>
      </div>
    </section>
</body>
</html>
```

### HTML(전체 범위)

`<html>`는 HTML 문서의 전체 범위를 지정

웹 브라우저가 해석해야 할 HTML 문서가 어디에서 시작하며, 어디에서 끝나는지 알려주는 역할

### HEAD(정보 범위)

웹 브라우저가 해석해야 할 HTML 문서의 정보 범위를 지정

여기서 말하는 정보에는 웹 페이지의 제목, 웹 페이지의 문자 인코딩 방식, 연결할 외부 파일의 위치, 웹 페이지를 구조화하기 위한 기본 세팅 값 같은 것들이 해당

### BODY(구조 범위)

웹 브라우저가 해석해야 할 HTML 문서의 구조 범위를 지정

구조는 사용자가 화면을 통해서 볼 수 있는 콘텐츠의 형태나 레이아웃 등을 의미 

로고, 헤더, 푸터, 내비게이션, 메뉴, 버튼, 입력창, 팝업, 광고 등 보이는 모든 것들이 구조에 해당

### DOCTYPE(DTD, 버전 지정)

DOCTYPE(DTD, Document Type Definition)은 마크업 언어에서 문서 형식을 정의

웹 브라우저에 우리가 제공할 HTML 문서를 어떤 HTML 버전의 해석 방식으로 구조화하면 되는지를 알려준다.(HTML은 크게 1, 2, 3, 4, X-, 5 버전이 있다.)

현재의 표준 모드는 HTML5

```html
<!-- HTML 5 -->
<!DOCTYPE html>

<!-- XHTML 1.0 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

## HTML 문서의 정보

### TITLE (웹 페이지의 제목)
HTML 문서의 제목을 정의한다. 웹 브라우저의 각 사이트 탭에서 이름으로 표시된다.

![탭이름](https://heropy.blog/images/screenshot/html-css-starter/browser_tabs.jpg)

```html
<head>
  <title>네이버</title>
</head>
```

### META(웹 페이지의 정보)
웹페이지에 관한 정보(표시 방식, 제작자, 내용, 키워드 등)를 검색엔진이나 브라우저에 제공한다. 빈(Empty) 태그이다.

```html
<head>
  <meta charset="UTF-8">
  <meta name="author" content="박지원">
  <meta name="description" content="내 사이트가 최고!">
</head>

<문서의정보범위>
  <정보 문자인코딩방식="UTF-8">
  <정보 정보종류="사이트제작자" 정보값="박지원">
  <정보 정보종류="사이트설명" 정보값="내 사이트가 최고!">
</문서의정보범위>
```

| 속성 | 의미 |	값 |
|------|------|----|
| charset |	문자인코딩 방식 |	UTF-8, EUC-KR 등 |
| name | 검색엔진 등에 제공하기 위한 정보의 종류(메타 데이터)	| author, description, keywords, viewport 등 |
| content |	name 이나 http-equiv 속성의 값을 제공 |	

`charset`은 텍스트가 출력되는 방식을 설정하는 속성이다.  

`UTF-8`은 아시아권 언어에 특화된 문자인코딩 방식이다.

### LINK(CSS 불러오기)
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

### STYLE (CSS 작성하기)

CSS를 HTML 문서 내부에 작성할 때 사용

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

### SCRIPT (JS 불러오거나 작성하기)
`<script></script>`로 JS를 `<link>`로 불러오거나 `<style></style>`안에 작성할 수 있다.

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

## HTML 문서의 구

### DIV(막 쓰는 태그)
`<div></div>`의 ‘div’는 ‘division’으로 약자로 ‘분할’을 뜻하고 문서의 부분이나 섹션을 정의한다. 

단순히 특정 범위를 묶는(wrap) 용도로 사용한다. 이렇게 묶인 부분들에 CSS나 JS를 적용한다.

```html
<body>
  <div>
    <p></p>
  </div>
  <div>
    <div>
      <h1></h1>
      <p></p>
    </div>
  </div>
</body>

<body>
  <묶음1>
    <p></p>
  </묶음1>
  <묶음2>
    <묶음2-1>
      <h1></h1>
      <p></p>
    </묶음2-1>
  </묶음2>
</body>
```

### IMG(이미지 넣는 태그)
`<img>`는 HTML에 이미지를 삽입할 때 사용한다.

```html
<body>
  <img src="./kitty.png" alt="고양이">
</body>

<body>
  <이미지 경로="./kitty.png" 대체텍스트="고양이">
</body>
```

| 속성 | 의미 |	값 |
|------|------|----|
| src | (필수)이미지의 URL | URL |
| alt |	(필수)이미지의 대체 텍스트(alternate)를 지정 |	

`src`, `alt`은 `<img>`를 사용할 때 반드시 포함되어야 할 속성이다.

만약 속성이 누락되었다면 이는 웹 표준에 어긋난다.

## 웹 표준 검사하기

[W3C validator](https://validator.w3.org/#validate_by_upload)에 접속해  HTML 문서가 표준에 부합하는지 테스트를 해볼 수 있다.

![https://heropy.blog/images/screenshot/html-css-starter/markup%20_validation_result_image_kytty.jpg](https://heropy.blog/images/screenshot/html-css-starter/markup%20_validation_result_image_kytty.jpg)

위에서 `<img src="./kitty.png">`라고 작성했을 때 나오는 결과이다. 

## HTML 예제

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>GitHub</title>
</head>
<body>
    <div class="header">
        <div class="container">
            <div class="container-left">
                <div class="logo">
                    <img src="https://heropcode.github.io/GitHub-Responsive/img/logo.svg" alt="GitHub Logo">
                </div>
                <div class="menu">
                    <div class="menu-item">Personal</div>
                    <div class="menu-item">Open Source</div>
                    <div class="menu-item">Business</div>
                    <div class="menu-item">Explore</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```
