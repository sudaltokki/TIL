# HTML 문서의 범위

```html
<!DOCTYPE html>
<html lang="ko">
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
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="author" content="박지원">
    <meta name="description" content="내 사이트">
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

## HTML(전체 범위)
`<html>`는 HTML 문서의 전체 범위를 지정  
웹 브라우저가 해석해야 할 HTML 문서가 어디에서 시작하며, 어디에서 끝나는지 알려주는 역할
```html
<html lang="국가 언어">
  .
  .
  .
</html>
```

### 국가 언어 설정

|속성 | 의미 | 값 |
|-----|------|----|
| lang | 문서의 언어 |	ko, en…|

[ISO 639-1 코드 목록](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D) 

## HEAD(정보 범위)

웹 브라우저가 해석해야 할 HTML 문서의 정보 범위를 지정

여기서 말하는 정보에는 웹 페이지의 제목, 문자 인코딩 방식, 연결할 외부 파일의 위치, 기본 세팅 값 같은 것들이 해당한다.

## BODY(구조 범위)

웹 브라우저가 해석해야 할 HTML 문서의 구조 범위를 지정

구조는 사용자가 화면을 통해서 볼 수 있는 콘텐츠의 형태나 레이아웃 등을 의미 

로고, 헤더, 푸터, 내비게이션, 메뉴, 버튼, 입력창, 팝업, 광고 등 보이는 모든 것들이 구조에 해당한다.

## DOCTYPE(DTD, 버전 지정)

DOCTYPE(DTD, Document Type Definition)은 마크업 언어에서 문서 형식을 정의하는 역할을 한다.

웹 브라우저에 우리가 제공할 HTML 문서를 어떤 HTML 버전의 해석 방식으로 구조화하면 되는지를 알려준다.  
HTML은 크게 1, 2, 3, 4, X-, 5 버전으로 나누어진다. (현재의 표준 모드는 HTML5)

```html
<!-- HTML 5 -->
<!DOCTYPE html>

<!-- XHTML 1.0 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```
