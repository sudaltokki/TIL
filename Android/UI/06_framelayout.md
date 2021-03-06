# Frame Layout
자식 뷰들끼리 겹칠 수 있는 layout 

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- LinearLayout에서는 자식 뷰들이 절대 겹칠 수 없다-->
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="#2196F3"
            android:text="hello"
            android:textSize="30dp"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="#FF9800"
            android:text="hello"
            android:textSize="30dp"/>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="#E91E63"
            android:text="hello"
            android:textSize="30dp"/>


    </LinearLayout>

    <!-- FrameLayout을 쓰면 자식 뷰들이 겹칠 수 있다-->
    <!-- 먼저 적은 뷰가 밑으로 간다-->
    <FrameLayout
        android:layout_marginTop="100dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <TextView
            android:layout_width="300dp"
            android:layout_height="300dp"
            android:background="#2196F3"
            android:text="hello"
            android:textSize="30dp"/>
        <TextView
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:background="#FF9800"
            android:text="hello"
            android:textSize="30dp"/>
        <TextView
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:background="#E91E63"
            android:text="hello"
            android:textSize="30dp"/>

    </FrameLayout>
</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130045597-33c6817b-8a35-4da1-a0f4-72cf38fdf046.png)

> Relative Layout도 자식 뷰들끼리 겹칠 수 있지만 연산과정이 더 많아 Frame Layout을 쓰는 것이 좋다.

## 실습

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    
    <FrameLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true">
        <!-- Relative Layout을 이용하기 때문에 부모 뷰를 기준으로 하는 속성을 사용할 수 있다-->
        <TextView
            android:layout_width="300dp"
            android:layout_height="300dp"
            android:background="#3F51B5"
            android:layout_gravity="center"/>

        <TextView
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:background="#673AB7"
            android:layout_gravity="center"/>

        <TextView
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:background="#03A9F4"
            android:layout_gravity="center"/>

    </FrameLayout>
</RelativeLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130046199-5ce7eaa5-8148-47e5-9aaa-b94912896453.png)

