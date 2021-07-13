# HTML 요소(Elements & Attributes) 총정리
> 패스트캠퍼스 강의를 듣고 학습한 내용을 기록합니다.  
> 참고한 블로그 [heropy.blog](https://heropy.blog/2019/04/24/html-css-starter/)

> 빈 태그(Empty Tags)는 <TAG />와 같이 /를 포함하여 표시합니다. 

## 주요 범위

### \<html>  
HTML 문서의 범위를 설정

|속성 | 의미 | 값 |
|-----|------|----|
| lang | 문서의 언어 |	ko, en…|

[ISO 639-1 코드 목록](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D)  
MDN / W3Schools

---

### \<head>
HTML 문서의 정보를 설정

MDN / W3Schools

---

### \<body>
HTML 문서의 구조를 설정

```
body { display: block; }  
```

MDN / W3Schools

---

## 메타데이터

### \<title>
브라우저의 제목 표시줄이나 페이지 탭에 보여지는 문서의 제목을 설정

MDN / W3Schools

---

### \<base />
HTML 문서에 포함된 모든 상대 URL들의 기준 URL를 설정

한 문서에 하나의 <base /> 요소만 포함 가능.

| 속성 | 의미 | 값 | 기본값 |
|------|------|----|--------|
|href| 기준 URL |	URL |	    |
|target| A 요소처럼 target 속성을 사용하는 요소의 기본값 |	_self, _blank | _self |

MDN / W3Schools

---

### \<link />
외부 리소스의 연결 및 현재 문서와의 관계를 명시 (HTML, CSS, ICON 등 가져오기)

| 속성 | 의미 |	값 |
|------|------|----|
| rel |	(필수)현재 문서와 외부 리소스와의 관계(Link Types) | stylesheet, icon… |	
| href |	외부 리소스의 URL |	URL	|
| type |	외부 리소스의 MIME 타입 |	text/css, image/x-icon…	|

MDN / W3Schools

---

### \<meta />
기타 메타데이터 요소(\<link />, \<style> 같은)로 나타낼 수 없는 메타데이터를 나타내기 위해 설정 (검색엔진이나 브라우저에 정보 제공)

| 속성 | 의미 |	값 |
|------|------|----|
| charset |	문자인코딩 방식 | UTF-8, EUC-KR… |
| name | 메타 데이터의 이름(정보의 종류)	| author, description… |
| http-equiv | 서버/사용자 에이전트의 작동방식 변경에 대한 지시(HTTP 응답 헤더 제공) |	refresh, X-UA-Compatible… |
| content |	name, http-equiv의 값 | |
  
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no, maximum-scale=1, minimum-scale=1" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
```
  
MDN / W3Schools

---

### \<style>
스타일 정보(CSS)를 설정

| 속성 | 의미 |	기본값 |
|------|------|--------|
| type | MIME 타입 | text/css |

MDN / W3Schools

---

## 콘텐츠 구분
  
### \<h1>, \<h2>, \<h3>, \<h4>, \<h5>, \<h6>
문서의 정보 계층을 구조화   
(Heading, 문서나 구분된 영역의 제목을 설정, 문서의 목차)

숫자가 낮을수록 높은 단계(중요한)의 제목.

```
h1, h2, h3, h4, h5, h6 { display: block; }
```

MDN / W3Schools

---

### \<header>
문서의 헤더를 설정 (보통 로고, 제목, 검색 등을 포함)

```
header { display: block; }
```

MDN / W3Schools

---

### \<footer>
문서의 푸터를 설정 (보통 작성자, 저작권, 관련 문서 등을 포함)

```
footer { display: block; }
```
  
MDN / W3Schools

---

### \<main>
문서의 주요 콘텐츠를 설정.

IE 지원 불가   
한 문서에 하나의 `\<main>` 요소만 포함 가능.

```
main { display: block; }
```
  
MDN / W3Schools

---

### \<article>
독립적으로 구분되거나 재사용 가능한 영역을 설정 (매거진/신문 기사, 블로그 등)

일반적으로 `\<h1>`~`\<h6>`를 포함하여 식별.  
작성일자와 시간을 `\<time>`의 datetime 속성으로 작성.

```
article { display: block; }
```

MDN / W3Schools

---

### \<section>
문서의 일반적인 영역을 설정.

일반적으로 `\<h1>`~`\<h6>`를 포함하여 식별.

```
section { display: block; }
```

MDN / W3Schools

---

### \<aside>
문서의 별도 콘텐츠를 설정.  
(보통 광고나 기타 링크 등의 사이드바(Side bar)를 설정)

```
aside { display: block; }
```

MDN / W3Schools

---

### \<nav>
다른 페이지 링크를 제공하는 영역을 설정.  
(Navigation, 보통 메뉴(Home, About, Contact), 목차, 색인 등을 설정)

```
nav { display: block; }
```

MDN / W3Schools

---

### \<address>
`\<body>`, `\<article>`, `\<footer>` 등에서 연락처 정보를 제공하기 위해 포함하여 사용.

```
address { display: block; }
```

MDN / W3Schools

---

### \<div>
본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정. (Division, 꾸미는 목적으로 사용)

```
div { display: block; }
```

MDN / W3Schools

---

## 문자 콘텐츠

### \<ol>, \<ul>, \<li>
각 항목(`\<li>`)의 정렬된 목록(`\<ol>`)이나 정렬되지 않은 목록(`\<ul>`)을 설정.  
(Ordered List, Unordered List, List Item, 순서가 필요하거나(`\<ol>`) 순서가 필요하지 않은(`\<ul>`) 목록을 정의)

`\<ol>`과 `\<ul>`은 자식으로 `\<li>`만 포함 가능.  
`\<li>`는 단독으로 사용할 수 없으며, `\<ol>`이나 `\<ul>`에 자식으로 포함되어야 함.  
정렬된 목록(`\<ol>`)의 항목 순서는 중요도를 의미할 수 있음.

```
ol, ul { display: block; }
li { display: list-item; }
```

OL: MDN / W3Schools
UL: MDN / W3Schools
LI: MDN / W3Schools

---

### \<ol>
정렬된 목록을 설정.

| 속성 | 의미 |	값 |
|------|------|----|
| start | 항목에 매겨지는 번호의 시작 값 |	숫자(Number) |	
| type | 항목에 매겨지는 번호의 유형|	a, A, i, I, 1 |

---

### \<li>
항목을 설정.

| 속성 | 의미 |	값 |	특징 |
|------|------|----|------|
| value |	항목의 순서를 설정 | 숫자(Number) |	이하 항목들의 순서가 다시 지정됨 |

---

### \<dl>, \<dt>, \<dd>
용어(`\<dt>`)와 정의(`\<dd>`) 쌍들의 영역(`\<dl>`)을 설정.  
(Description List, Definition Details, Definition Term)

`\<dl>`은 `\<dd>`, `\<dt>`만을 포함해야 함.  
키(key)/값(value) 형태를 표시할 때 유용.

```
<dl>
  <dt>Coffee</dt>
  <dd>Coffee is a brewed drink prepared from roasted coffee beans, the seeds of berries from certain Coffea species.</dd>
  <dt>Milk</dt>
  <dd>Milk is a nutrient-rich, white liquid food produced by the mammary glands of mammals.</dd>
</dl>
```

```
dl, dt, dd { display: block; }
```

DL: MDN / W3Schools
DT: MDN / W3Schools
DD: MDN / W3Schools

---

### \<p>
하나의 문단을 설정. (Paragraph)

일반적으로 정보통신보조기기 등은 다음 문단(`\<p>`)으로 넘어갈 수 있는 단축키를 제공함.

```
p { display: block; }
```

MDN / W3Schools

---

### \<hr />
문단의 분리(주제에 의한)를 위해 설정. (Horizontal Rule)

대부분의 경우 수평선(border)으로 표시(표현적 관점)되나 의미적 관점으로만 사용해야 함.

```
hr { display: block; }
```

MDN / W3Schools

---

### \<pre>
서식이 미리 지정된 텍스트를 설정. (Preformatted Text)

텍스트의 공백과 줄바꿈을 유지하여 표시할 수 있음.  
기본적으로 Monospace 글꼴 계열로 표시됨.

```
pre { display: block; }
```

MDN / W3Schools

---

### \<blockquote>
일반적인 인용문을 설정. (Block Quotation)

| 속성 | 의미 |	값 |
|------|------|----|
| cite | 인용된 정보의 URL | URL |

```
blockquote { display: block; }
```

MDN / W3Schools

---

## 인라인 텍스트

### \<a>
다른 페이지, 같은 페이지 위치(#, 해시 태그), 파일, 이메일 주소, 전화번호 등 다른 URL로 연결할 수 있는 하이퍼링크를 설정.  
(Anchor, 외부로 내보내기)

| 속성 | 의미 |	값 | 기본값 |	특징 |
|------|------|----|--------|------|
| download | 이 요소가 리소스를 다운로드하는 용도로 사용됨을 의미 | 불린(Boolean) |
| href | 링크 | URL |	URL | 생략 가능 |
| rel |	현재 문서와 링크 URL의 관계(Link Types) |	license, prev, next… |	
| target | 링크 URL의 표시(브라우저 탭) 위치 | _self, _blank 	| _self |	
|type |	링크 URL의 MIME 타입 |	text/html… |		

```
a { display: inline; }
```

MDN / W3Schools

---

### \<abbr>
약어를 지정. (Abbreviation, 보통 title 속성을 사용하여 전체 글자나 설명을 제공)

```
Using <abbr title="HyperText Markup Language">HTML</abbr> is fun and easy!
```

```
abbr { display: inline; }
```

MDN / W3Schools

---

### \<b>
문체가 다른 글자의 범위를 설정. (Bring Attention)

특별한 의미를 가지지 않음.  
읽기 흐름에 도움을 주는 용도로 사용.  
다른 태그가 적합하지 않은 경우 마지막 수단으로 사용.  
기본적으로 글자가 두껍게(Bold) 표시됨.

```
b { display: inline; }
```

MDN / W3Schools

---

### \<mark>
사용자의 관심을 끌기 위해 하이라이팅할 때 사용.  
(Mark Text, 형광펜을 사용하여 관심있는 부분을 표시하는 것과 같은 의미)

기본적으로 형광펜을 사용한 것처럼 글자 배경이 노란색(Yellow)으로 표시됨.

```
mark { display: inline; }
```

MDN / W3Schools

---

### \<em>
단순한 의미 강조를 표시. (Emphasis)

중첩이 가능.  
중첩될수록 강조 의미가 강해짐.  
정보통신보조기기 등에서 구두 강조로 발음됨.  
기본적으로 이탤릭체(Italic type)로 표시됨.

```
em { display: inline; }
```

MDN / W3Schools

---

### \<strong>
의미의 중요성을 나타내기 위해 사용. (Strong Importance)

기본적으로 글자가 두껍게(Bold) 표시됨.

```
strong { display: inline; }
```

MDN / W3Schools

---

### \<i>
`\<em>`, `\<strong>`, `\<mark>`, `\<cite>`, `\<dfn>` 등에서 표현할 수 있는 적합한 의미가 아닌 경우 사용.  
(평범한 글자와 구분(아이콘이나 특수기호 같은)하기 위해 사용)

기본적으로 이탤릭체(Italic type)로 표시됨.

```
i { display: inline; }
```

MDN / W3Schools

---

### \<dfn>
용어를 정의할 때 사용.
(Definition)

```
dfn { display: inline; }
```

MDN / W3Schools

---

### \<cite>
창작물에 대한 참조를 설정.
(책, 논문, 영화, TV 프로그램, 노래, 게임 등의 제목)

기본적으로 이탤릭체(Italic type)로 표시됨.

```
<cite>The Scream</cite> by Edward Munch. Painted in 1893.
```

```
cite { display: inline; }
```

MDN / W3Schools

---

### \<q>
짦은 인용문을 설정.
(Inline Quotation)

긴 인용문을 설정할 경우 `\<blockquote>`를 사용.

| 속성 | 의미 | 값 |
|------|------|----|
| cite | 인용된 정보의 URL | URL |

```
q { display: inline; }
```

MDN / W3Schools

---

### \<u>
밑줄이 있는 글자를 설정.
(Underline)

순수하게 꾸미는 용도의 요소로 사용.  
`\<a>`와 헷갈릴 수 있는 위치에서 사용하지 않도록 주의.  
`\<span style="text-decoration: underline;">`을 활용할 수 있을 경우에는 사용을 권장하지 않음.

```
u { display: inline; }
```

MDN / W3Schools

---

### \<code>
컴퓨터 코드 범위를 설정.
(Inline Code)

`\<code>document.getElementById('id-value')</code> is a piece of computer code.`

기본적으로 고정폭(Monospace) 글꼴 계열로 표시됨.

```
code { display: inline; }
```

MDN / W3Schools

---

### \<kbd>
텍스트 입력 장치(키보드)에서 사용자 입력을 나타내는 텍스트 범위를 설정.
(Keyboard Input)

```
<p><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>K</kbd></p>, <kbd>ESC</kbd>
```

```
kbd { display: inline; }
```

MDN / W3Schools

---

### \<sup>, \<sub>
위 첨자(`\<sup>`)와 아래 첨자(`\<sub>`)를 설정.
(Superscripted text, Subscript text)

```
X<sup>4</sup> + Y<sup>2</sup>, H<sub>2</sub>O
```

```
sup, sub { display: inline; }
```

SUP: MDN / W3Schools
SUB: MDN / W3Schools

---

### \<time>
날짜나 시간을 나타내기 위한 목적으로 사용.

| 속성 | 의미 |	값 |
|------|------|----|
| datetime | 유효한 날짜 문자 | Date |

IE 지원 불가

```
<p>The Cure will be celebrating their 40th anniversary on <time datetime="2018-07-07">July 7</time> in London's Hyde Park.</p>
```

```
time { display: inline; }
```

MDN / W3Schools

---

### \<span>
본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정.

```
span { display: inline; }
```

MDN / W3Schools 

---

### \<br />
줄바꿈을 설정.

```
br { display: inline; }
```

MDN / W3Schools

---

## 수정

### \<del>
삭제된(변경된) 텍스트의 범위를 지정.

| 속성 | 의미 |	값 |
|------|------|----|
| cite | 변경을 설명하는 리소스의 URI | URI |
| datetime | 변경이 일어난 유요한 날짜 문자 | Date |

```
del { display: inline; }
```

MDN / W3Schools

---

### \<ins>
새로 추가된(변경된) 텍스트의 범위를 지정.

| 속성 | 의미	| 값 |
|------|------|----|
| cite | 변경을 설명하는 리소스의 URI | URI |
| datetime | 변경이 일어난 유요한 날짜 문자 | Date |

```
ins { display: inline; }
```

MDN / W3Schools
