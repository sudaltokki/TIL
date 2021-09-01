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
