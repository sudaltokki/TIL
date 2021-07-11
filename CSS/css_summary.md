# CSS 개요
> 패스트캠퍼스 강의를 듣고 학습한 내용을 기록합니다.  
> 참고한 블로그 [heropy.blog](https://heropy.blog/2019/04/24/html-css-starter/)

## CSS 문법
선택자, 속성, 값이 있으며 무엇을 의미하는지 이해하는 것이 중요하다.

```css
div {
  font-size: 20px;
  color: red;
}

선택자 {
  속성: 값;
  속성: 값;
}
```

### 선택자의 역할
선택자는 HTML에 스타일(CSS)을 적용하기 위해 HTML의 특정한 요소를 선택하는 사인(sign)이다.

```html
<div>
  <h1>제목..</h1>
  <p>본문..</p>
</div>

```

```css
h1 {
  color: red; /*빨강 글자색(CSS, color: red;)을 제목(HTML, <h1></h1>)에 적용*/
}
p {
  color: blue; /*파랑 글자색(CSS, color: blue;)을 본문(HTML, <p></p>)에 적용*/
}

```

### 속성(Properties)과 값(Value)

```css
div {
  color: red; /* 글자색은 빨강 */
  font-size: 20px; /* 글자 크기는 20px */
  width: 300px; /* 가로 너비는 300px */
  margin: 20px; /* 바깥 여백은 20px */
  padding: 10px 20px; /* 안쪽 여백은 위아래 10px, 좌우 20px */
}
```
속성과 값은 스타일을 지정할 때 사용한다.
> 속성과 값은 많이 아는 것이 중요하다. 

## CSS 선언 방식

### 태그에 직접 작성하기(인라인)

```html
<div style="color: red;">태그에 직접 작성1</div> 
<div style="color: red;">태그에 직접 작성2</div>
<div style="color: red;">태그에 직접 작성3</div> 
<div style="color: red;">태그에 직접 작성4</div> 
```
이 방법은 HTML 태그에 직접 작성하기 때문에 선택자가 필요하지 않다.
하지만 직접 태그를 찾아서 작성해야한다는 단점이 있다.

### HTML에 포함하기(내장)
CSS만 따로 작성하기 때문에 선택자가 필요하다. 

CSS 코드가 HTML의 `<style></style>` 안에 포함되어 있다.

```html
<head>
  <style>
    div {
      color: red;
    }
  </style>
</head>
<body>
  <div>HTML에 포함1</div> 
  <div>HTML에 포함2</div> 
  <div>HTML에 포함3</div> 
</body>
```

### HTML 외부에서 불러오기
CSS 코드를 완전히 분리할 수 있다. 하나의 CSS 파일을 여러 HTML 파일이 불러와서 사용할 수 있다.

```html
<!-- HTML 1 -->
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기1</div> 
</body>
```

```html
<!-- HTML 2 -->
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기2</div> 
</body>
```

```css
/* main.css */
div {
  color: red;
}
```

## 선택자
선택자는 HTML의 특정한 요소를 선택하는 사인(sign)이다.

### 태그로 선택하기
선택자를 입력하는 부분에 적용하려는 태그의 이름을 입력합니다.

```css
h1 {
  color: red;
}

p {
  color: blue;
}
```

```html
<h1>제목1</h1> <!--red-->
<h1>제목2</h1> <!--red-->
<p>본문1</p> <!--blue-->
<p>본문2</p> <!--blue-->
```

### 클래스로 선택하기
좀 더 명확하게 원하는 요소를 찾을 수 있다.

```css
/*class="title"은 글자색이 빨강이야!*/
.title {
  color: red;
}
/*class="main-text"는 글자색이 파랑이야!*/
.main-text {
  color: blue;
}
```

```html
<h1 class="title">제목1</h1> <!--red-->
<h1>제목2</h1>
<p class="main-text">본문1</p> <!--blue-->
<p>본문2</p
```

CSS의 `.title`은 HTML의 `class="title"`와 동일하다. `.`이 없는 선택자 `title`은 태그 `<title>`를 의미하게 되니 전혀 다른 뜻이다.

> 클래스를 선택자로 사용할 때 . 을 누락하지 않도록 조심하자.

## 속성


### 크기

* **width (가로 너비)**  
요소의 가로 너비를 지정한다. 단위는 `px`(pixels)을 사용

```css
div {
  width: 300px;
  요소가로너비: 너비값;
}
```

* **height (세로 너비)**  
요소의 세로 너비를 지정

```css
div {
  height: 150px;
  요소세로너비: 너비값;
}
```

* **font-size (글자 크기)**   
요소 내용(Text)의 글자 크기를 지정 (기본값 = 16px)

```css
div {
  font-size: 16px;
  글자크기: 크기값;
}
```

### 여백

* **margin (요소의 바깥 여백)**   

요소의 바깥 여백을 지정한다. 바깥 여백은 요소와 요소 사이의 여백(거리, 공간)을 생성할 때 사용한다.

```css
div {
  margin: 20px;
  요소바깥여백: 여백값;
}
```

위 코드는 `margin`은 요소의 위, 아래, 좌, 우 모두 `20px`의 여백을 지정하겠다는 의미

```css
div {
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  margin-left: 20px;
  요소바깥여백-위쪽: 여백값;
  요소바깥여백-오른쪽: 여백값;
  요소바깥여백-아래쪽: 여백값;
  요소바깥여백-왼쪽: 여백값;
}
```

이렇게 세분화해서 작성할 수도 있다.

* **padding (요소의 내부 여백)**  
요소의 내부 여백을 지정한다. 내부 여백은 자식 요소를 감싸는 여백을 의미한다.

```css
div {
  padding: 20px;
  요소내부여백: 여백값;

```

```css
div {
  padding-top: 20px;
  padding-right: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
  요소내부여백-위쪽: 여백값;
  요소내부여백-오른쪽: 여백값;
  요소내부여백-아래쪽: 여백값;
  요소내부여백-왼쪽: 여백값;
}
```

마찬가지로 세분화해서 한 방향씩 지정이 가능하다.

### 색상

* **color (글자 색상)**

요소 내용(Text)의 글자 색상을 지정한다.

```css
div {
  color: red;
  글자색상: 빨강;
}
```

> `font-color`, `text-color` 이란 속성은 없다.

* **background (요소 색상)**

요소의 배경 색상을 지정한다. `color`는 글자의 색만 지정할 수 있으며, 요소의 (배경)색을 바꾸려면 `background-color`가 필요하다.  

```css
div {
  background-color: red;
  요소배경: 빨강;
}
```

## CSS 예제

**`example1`** 디렉터리 안에  **`main.css`** 파일을 생성후 연결

```html
<head>
  <!-- 생략... -->
  <link rel="stylesheet" href="./css/main.css">
</head>
```

```css
body {
  /* 브라우저마다 기본 설정으로 BODY 요소에 margin과 padding의 값이 설정되어 있습니다. */
  /* 각각의 브라우저마다 BODY 요소가 다른 값을 가지고 있을 수 있으므로 우리가 일정하게 초기화해서 사용합니다. */
  /* 0은 단위를 사용하지 않습니다. */
  margin: 0;
  padding: 0;
}
.header {
  /* 화면에는 다음의 값으로 랜더링 되어 있는데 여러 이유로(설명이 많이 필요합니다) 생략 가능합니다. */
  /* width: 100%; */
  /* height: 75px; */
  background-color: white;
  border-bottom: 1px solid lightgray; /* 요소테두리선-아래: 1px두께 가는실선 밝은회색; - header 하단에 회색의 선이 표시됩니다. */
}
.container {
  /* height: 75px; */
  width: 980px;
  margin: auto; /* 요소바깥여백: 여백자동; - 이 속성과 값은 container를 수평 가운데 정렬하는 속성으로 쓰입니다. */
}
.container-left {
  /* width: 370px; */
  /* height: 75px; */
  /* float: left; */
  padding-top: 20px;
  padding-bottom: 20px;
}
.logo {
  margin-right: 5px;
  float: left; /* 수평정렬: 왼쪽부터차례대로; - logo와 menu를 수평 정렬하기 위해 사용되었습니다. 이 속성의 정확한 의미는 수평 정렬이 아니지만 쉽게 이해하도록 의역했습니다. */
}
.logo img { /* logo의 자식(후손) 요소인 img 태그 - 선택자에서 띄어쓰기는 자식(후손)요소를 의미합니다. */
  display: block; /* 요소특성: 형태위주; - img(이미지) 하단에 생기는 불필요한 여백을 없애기 위해서 사용되었습니다. */
}
.menu {
  float: left; /* logo와 menu를 수평 정렬하기 위해 사용되었습니다. */
}
.menu-item {
  font-size: 16px;
  padding: 8px 10px; /* padding-top: 8px; padding-bottom: 8px; padding-left: 10px; padding-right: 10px; 과 같습니다. */
  float: left; /* 각 menu-item들을 수평 정렬하기 위해 사용되었습니다. */
  line-height: 1; /* 줄 높이, 행간과 비슷한 개념으로 이해할 수 있습니다. 기본 값은 normal이며 이는 약 1.2배 정도입니다. 그대로 유지하면 .menu-item의 높이가 약 35px이 되기 때문에 1배로 수정하여 32px로 .logo의 크기와 동일하게 작업합니다. */
}

/* float: left; 를 사용하고 마무리할 때 필요한 코드입니다. */
/* float: left;를 사용한 해당 HTML 요소의 부모 요소에게 class="clearfix"를 입력하여 CSS float 속성에서 발생하는 현상을 해제합니다. */
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```
