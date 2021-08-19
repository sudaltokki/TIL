# Linear Layout
> 자식 component를 수직이나 수평으로 나열하는 layout

layout에 관한 component는 대부분 부모 component가 될 수 있는 component

* 부모 component의 특징  
보통 화면에 나오지 않고 자식 컴포넌트를 배치, 화면의 구성을 정한다  
ex) 어떤 뷰를 수직으로 나열, 위 아래 배치

* 자식 component의 특징
화면에 실질적으로 나오는 부분, 배치를 정할 순 없음

![image](https://user-images.githubusercontent.com/86659995/129850391-4d4d08f3-bb2e-4760-a220-08b8904f137e.png)

LinearLayout이 부모 컴포넌트로 사용  
LinearLayout에 의해 두 텍스트 뷰의 위치가 정해짐  
orientation를 vertical로 하면 자식 component를 수직으로 나열, horizental로 하면 수평으로 나열  
같은 속성이 적용 되면 범위가 더 작은 것이 적용 (자식 것이 적용)


wrap_component : component에 해당하는 부분만큼 크기를 지정  
match_parent : 부모 component에 크기를 맞춘다  
android:layout_gravity : Linearlayout의 속성, center right left 등을 통해 위치 설정

## 실습

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:gravity="center"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="20dp"
        android:text="가운데"/>

    <!--    layout_gravity : 부모 클래스 기준으로 텍스트 뷰가 어디로 갈지 정하는 것-->
    <!--    gravity : 이 텍스트 뷰 가지고 있는 컨텐트를 어디로 보낼 지-->
    <!--    두가지 속성 모두 적용 : right|bottom-->
    <TextView
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:text="Gravity"
        android:gravity="right|bottom"
        />

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="#3F51B5"
            android:text="100"
            android:textSize="20dp" />
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:orientation="horizontal">

        <!--비율로 나열하고 싶을 때는 layout_weight 사용-->
        <!--이렇게 layout_weight를 1로 두면 가로크기가 1:1:1로 나열됨-->
        <!-- layout_weight 설정시 layout_width나 height를 0dp로 설정-->
        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:background="#CDDC39"
            android:text="200"
            android:textSize="20dp" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:textSize="20dp"
            android:text="200"
            android:background="#673AB7" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:background="#3F51B5"
            android:text="100"
            android:textSize="20dp"/>


    </LinearLayout>

    <!-- 이렇게 layout_weight를 1로 두면 세로크기가 1:1:1로 나열됨-->
    <!-- weightSum: 전체 비율 - 5개 나눈것 중에 나눠먹음-->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="300dp"
        android:orientation="vertical"
        android:weightSum="5">

        <TextView
            android:layout_weight="1"
            android:layout_width="wrap_content"
            android:layout_height="0dp"
            android:textSize="20dp"
            android:text="200"
            android:background="#CDDC39"/>
        <TextView
            android:layout_weight="1"
            android:layout_width="wrap_content"
            android:layout_height="0dp"
            android:textSize="20dp"
            android:text="200"
            android:background="#673AB7" />
        <TextView
            android:layout_weight="1"
            android:layout_width="wrap_content"
            android:layout_height="0dp"
            android:background="#3F51B5"
            android:text="100"
            android:textSize="20dp"/>


    </LinearLayout>



</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/129866394-e88a7649-6400-4412-b70b-3cc188335ead.png)

## 과제

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">

        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#CDDC39" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#F44336" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#FFC107" />


    </LinearLayout>

    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">

        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#009688" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#673AB7" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#2196F3" />


    </LinearLayout>

    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">

        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#780C44" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#000000" />
        <TextView
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:background="#181A8A" />


    </LinearLayout>


</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/129867905-ff936900-fae2-43b3-8072-b6fcca6f2c93.png)
