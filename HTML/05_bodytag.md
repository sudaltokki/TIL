# BODY 태그
HTML 문서의 구조

## \<div>
**div**는 division의 약자로 ‘분할’을 뜻하고 문서의 부분이나 섹션을 정의한다.   
단순히 특정 범위를 묶는(wrap) 용도로 사용한다. 이렇게 묶인 부분들에 CSS나 JS를 적용한다.

```html
<body>
  <div>
    <p></p>
  </div>
  <div>
      <p></p>
  </div>
</body>

<body>
  <묶음1>
    <p></p>
  </묶음1>
  <묶음2>
      <p></p>
  </묶음2>
</body>
```

## IMG(이미지 넣는 태그)
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

# 웹 표준 검사하기

[W3C validator](https://validator.w3.org/#validate_by_upload)에 접속해  HTML 문서가 표준에 부합하는지 테스트를 해볼 수 있다.

![https://heropy.blog/images/screenshot/html-css-starter/markup%20_validation_result_image_kytty.jpg](https://heropy.blog/images/screenshot/html-css-starter/markup%20_validation_result_image_kytty.jpg)

위에서 `<img src="./kitty.png">`라고 작성했을 때 나오는 결과이다. 
