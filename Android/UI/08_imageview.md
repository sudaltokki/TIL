# Image View

저해상도 핸드폰은 고해상도 이미지를 그리는 데 시간이 오래걸린다.  
Android Drawble Importer라는 플러그인을 사용해 해상도별 이미지를 만들고, 스마트폰 해상도에 따라 다른 사진을 보여줄 수 있다.   
>  플러그인 (plugin) - 안드로이드 스튜디오에서 기본적으로 제공하지 않는 기능을 제공
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

<!--    src로 이미지 경로 지정-->
<!--    이미지는 크기를 지정 : 어떤 디바이스에서 크게 보이거나 작게 보이진 않음-->
<!--    저해상도 핸드폰 : 고해상도 이미지를 그리는데 오래걸림-->
<!--    해상도 별로 준비된 이미지를 환경에 따라 자동으로 선택-->

   <ImageView
       android:layout_width="300dp"
       android:layout_height="300dp"
       android:src="@drawable/ic_launcher_foreground"/>

<!--    scaleType은 뷰 영역에 맞게 이미지를 확대, 축소하는 속성-->
   <ImageView
       android:layout_width="200dp"
       android:layout_height="200dp"
       android:background="#03A9F4"
       android:scaleType="centerCrop"
      android:src="@drawable/dog"/>

</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130102073-8439aa09-a781-478c-ae1b-f6e75c565963.png)

> scaleType 속성 - [블로그](https://blog.naver.com/beakdukhoo/222445968284)
