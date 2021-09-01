# 속성

## 크기

### width (가로 너비)
요소의 가로 너비를 지정, 단위는 **px(pixels)**

```css
div {
  width: 300px;
  요소가로너비: 너비값;
}
```

### height (세로 너비)
요소의 세로 너비를 지정

```css
div {
  height: 150px;
  요소세로너비: 너비값;
}
```

### font-size (글자 크기)  
요소 내용(Text)의 글자 크기를 지정 (기본값 = 16px)

```css
div {
  font-size: 16px;
  글자크기: 크기값;
}
```

## 여백

### margin (요소의 바깥 여백)
요소의 바깥 여백을 지정  
바깥 여백은 요소와 요소 사이의 여백(거리, 공간)을 생성할 때 사용한다.

```css
div {
  margin: 20px;
  요소바깥여백: 여백값;
}
```

위 코드는 요소의 위, 아래, 좌, 우 모두 20px의 여백을 지정하겠다는 의미이다.

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

똑같은 의미이지만 이렇게 세분화해서 작성할 수도 있다.

### padding (요소의 내부 여백)
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

## 색상

### color (글자 색상)
요소 내용(Text)의 글자 색상을 지정

```css
div {
  color: red;
  글자색상: 빨강;
}
```

> `font-color`, `text-color` 이란 속성은 없다.

### background (요소 색상)
요소의 배경 색상을 지정
`color`는 글자의 색을 지정하는 속성이며, 요소의 배경 색을 바꾸려면 `background-color`가 필요하다.  

```css
div {
  background-color: red;
  요소배경: 빨강;
}
```

## CSS 예제
html 파일이 들어있는 디렉터리 안에 css 파일을 생성한 후 <link>를 이용해 연결한다.

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>GitHub</title>
    <link rel="stylesheet" href="./css/main.css">
</head>

<body>
    <div class="header">
        <div class="container">
            <div class="container-left clearfix">
                <div class="logo">
                    <img src="https://heropcode.github.io/GitHub-Responsive/img/logo.svg" alt="GitHub Logo">
                </div>
                <div class="menu clearfix"> <!--menu 와 clearfix 모두 class 별칭이다-->
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

```css
body {
    /* 브라우저마다 기본 설정으로 BODY 요소에 margin과 padding의 값이 설정되어 있습니다. */
    /* 각각의 브라우저마다 BODY 요소가 다른 값을 가지고 있을 수 있으므로 우리가 일정하게 초기화해서 사용합니다. */
    margin: 0;
    padding: 0;
}

.header {
    width: auto; /*현재 가로의 길이는 100%*/
    height: auto; /*높이는 (로고의 높이)+(메뉴의 높이)*/
    /* 위 두 줄은 작성하지 않아도 기본값으로 설정되어 있습니다. */
    background-color: white;
    border-bottom: 1px solid lightgray; /*  header 하단에 회색의 선이 표시됩니다. */
}

.container {
    width: 980px;
    margin: auto;
}

.container-left {
    padding: 20px 0;
    /* 바깥쪽 좌우 여백을 설정해 container를 수평 가운데 정렬하는 속성으로 쓰입니다. */
    /* padding값은 같은 효과를 볼 수 있는 요소 중 가장 최하위 요소에 적용하는 것이 좋습니다. */
}

.logo {
    float: left; /* logo와 menu를 수평 정렬하기 위해 사용되었습니다. */
    margin-right: 5px; 
}

.logo img {
    /* logo의 자식 요소인 img 태그 - 선택자에서 띄어쓰기는 자식 요소를 의미합니다. */
    display: block; /*이미지 하단에 생기는 불필요한 여백을 없애기 위하여 사용되었습니다.*/
}

.menu {
    float: left; /* logo와 menu를 수평 정렬하기 위해 사용되었습니다. */
}

.menu-item {
    float: left;
    /* 각 menu-item들을 수평 정렬하기 위해 사용되었습니다. */
    /* margin-right: 10px; item마다 오른쪽에 10px만큼 여백이 생깁니다.*/
    padding: 8px 10px;
    /* item마다 내부 여백을 설정해서 수직 정렬하기 위해 사용되었습니다. */
    /* padding-top: 8px; padding-bottom: 8px; padding-left: 10px; padding-right: 10px; 과 같습니다. */
}

.clearfix::after {
    /* float: left; 를 사용하고 마무리할 때 필요한 코드입니다. */
    /* float: left;를 사용한 해당 HTML 요소의 부모 요소에게 class="clearfix"를 입력하여 CSS float 속성에서 발생하는 현상을 해제합니다. */
    content: "";
    display: block;
    clear: both;
}
```

 > 궁금한 내용을 검색할 때에는 html div tag mdn 혹은 css background mdn과 같이 ‘MDN’를 함께 검색하자.   
MDN 웹 문서는 모질라(파이어폭스 웹 브라우저)의 공식 웹사이트로 대부분 문서에서 여러 설명과 예제 그리고 한글을 지원하며 신뢰도가 높다.    
W3Schools 웹사이트는 MDN과 다르게 영리 목적(배너 광고 등)의 사이트이지만 입문자가 접하기에 좋게 잘 구성되어 있다.   
단, 정보의 신뢰도는 MDN보다 떨어진다.
