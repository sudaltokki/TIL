# 안드로이드에서 화면을 그리는 방법

## UI (User Interface) 
이용자 인터페이스  
휴대폰, 컴퓨터, 내비게이션 등 디지털 기기를 작동시키는 명령어나 기법을 포함하는 사용자 환경

## XML
DSL Language -> Domain Specific Language  
안드로이드 UI 를 그리기 위해 특화된 언어이다

## 핸드폰마다 화면 크기가 다 다른데 어떻게 화면을 그려야 할까?
> 픽셀, dpi, dp 단위

* 픽셀  
핸드폰 화면에서 빛이 나오는 전구, 가장 작은 단위

* dpi (dot per inch)

      - ldpi -> 120 (1인치에 120픽셀)

      - mdpi -> 160

      - hdpi -> 240

      - xhdpi -> 320

      - xxhdpi -> 480

      - xxhdpi -> 640

* dp (Density Independent Pixel)  
픽셀 독립적인 단위
화면을 통일시키기 위해서는 dp라는 단위로 통일시켜야한다.
