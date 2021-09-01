# HEAD 태그와 메타데이터
> 메타데이터(Meta Data) : 데이터에 관해 구조화된 데이터, 데이터를 설명해 주는 데이터  
> \<head> 요소 안에 기계가 식별할 수 있는 문서 정보(메타데이터)를 담는다.

> 빈 태그(Empty Tags)는 <TAG />와 같이 /를 포함하여 표시

## \<head>
웹 브라우저가 해석해야 할 HTML 문서의 정보 범위를 지정

```html
<head>
    <meta charset="UTF-8">
    <meta name="author" content="박지원">
    <meta name="description" content="내 사이트">
    <meta name="viewport" content="width=device-width", initial-scale=1.0>
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>내 사이트</title>
    <link rel="stylesheet" href="./css/main.css">
    <script src="./js/main.js"></script>
</head>
```

## \<title> 
HTML 문서의 제목, 브라우저의 제목 표시줄이나 페이지 탭에 보여지는 문서의 제목을 설정

<img src="https://heropy.blog/images/screenshot/html-css-starter/browser_tabs.jpg" width="800" height="50"/>

```html
<head>
  <title>내 사이트</title>
</head>
```

## \<style> (CSS 작성하기)
CSS를 HTML 문서 내부에 작성  

```html
<style>
  img {
    width: 100px;
    height: 200px;
  }
</style>
```

| 속성 | 의미 |	기본값 |
|------|------|--------|
| type | MIME 타입 | text/css |

> type은 자동으로 인식하기 때문에 생략이 가능하다.

> style 태그를 head 태그 말고도 body 태그에도 작성할 수는 있지만, 비효율적이기 때문에 추천하지 않는다.

## \<link /> (불러오기)
외부 리소스의 연결 및 현재 문서와의 관계를 명시 (HTML, CSS, ICON 등 가져오기)

```html
<head>
  <link rel="stylesheet" href="./css/main.css">
  <link rel="icon" href="./favicon.png">
</head>
```

| 속성 | 의미 |	값 |
|------|------|----|
| rel |	(필수)현재 문서와 외부 리소스와의 관계(Link Types) | stylesheet, icon 등 |	
| href |	외부 리소스의 URL |	URL	|
| type |	외부 리소스의 MIME 타입 |	text/css, image/x-icon…	|

> rel = relationship (관계) , href = hyperlink (하이퍼링크)

> \<style>과 마찬가지로 type은 자동으로 인식하기 때문에 생략이 가능하다.

## \<script> (JS 불러오기, JS 작성하기)
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
```

## \<base />
HTML 문서에 포함된 모든 상대 URL들의 기준 URL를 설정  
한 문서에 하나의 <base /> 요소만 포함 가능

| 속성 | 의미 | 값 | 기본값 |
|------|------|----|--------|
|href| 기준 URL |	URL |	    |
|target| A 요소처럼 target 속성을 사용하는 요소의 기본값 |	_self, _blank | _self |

## \<meta />
\<meta> 요소는 \<base>, \<link>, \<script>, \<style>, \<title>과 같은 다른 메타데이터 요소로 나타낼 수 없는 메타데이터를 나타낸다.

```html
<head>
  <meta charset="UTF-8">
  <meta name="author" content="박지원">
  <meta name="description" content="내 사이트">
  <meta name="viewport" content="width=device-width", initial-scale=1.0>
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
</head>
```
    
| 속성 | 의미 |	값 |
|------|------|----|
| charset |	문자인코딩 방식 | UTF-8, EUC-KR… |
| name | 메타 데이터의 이름(정보의 종류)	| author, description, keywords, viewport 등|
| http-equiv | 서버/사용자 에이전트의 작동방식 변경에 대한 지시(HTTP 응답 헤더 제공) |	refresh, X-UA-Compatible… |
| content |	name, http-equiv의 값 |

---

### charset
> character set    

Title보다 문자 인코딩 방식을 먼저 설정하는 것이 좋다.  
**UTF-8**은 아시아권 언어에 특화된 문자인코딩 방식이다.  
**EUC-KR**도 한글을 나타내는 문자 인코딩 방식이지만, 두 방식이 한글을 만드는 데에는 차이가 있다.

* EUC-KR : 완성형
박지원이라는 글자를 조합할 때 박 + 지 + 원 과같이 음절 단위로 조합한다.  
만약 완성된 조합이 없는 경우에 한글이 깨지는 현상이 발생한다.

* UTF-8 : 조합형
박지원이라는 글자를 조합할 때  ㅂ + ㅏ + ㄱ + ㅈ + ㅣ + ㅇ + ㅜ + ㅓ+  ㄴ과 같이 자음, 모음을 이용해 조합한다.  
EUC-KR보다 이 방식을 사용하는 것을 추천한다.

---

### viewport 
반응형 웹사이트를 제공하기 위해 필요한 코드, 화면의 정보를 렌더링하기 위한 영역을 설정한다.

---

### http-equiv
> http equivalent

서버나 사용자의 환경의 작동방식을 변경해주는 지시사항을 정의한다.  
인터넷 익스플로러 브라우저에서 우리가 사용하는 웹 사이트가 어떤 버전에서 최적화되어서 나올 수 있는지 렌더링 방식을 명시해준다.

> 한 태그 안에서 name과 http equiv 속성을 동시에 사용할 수 없다
