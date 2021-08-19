# Scroll View

스크롤을 할 수 있게 만들어 주는 뷰  
**스크롤 뷰는 하나의 자식 뷰만 가질 수 있다**  
따라서 자식 뷰를 여러 개 넣고 싶을 때는 LinearLayout 등의 다른 뷰 컨테이너를 활용하면 된다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- layout_width  크기 안에서만 scroll 작동 -->
    <!-- scrollbars="none" : 스크롤바 제거 -->
    <!-- fillViewport : true 없으면 정상적으로 작동하지 않을 수 있다 -->

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="500dp"
        android:fillViewport="true"
        android:scrollbars="none">

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:layout_width="300dp"
                android:layout_height="300dp"
                android:background="#F44336" />

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:background="#FFC107" />

            <TextView
                android:layout_width="100dp"
                android:layout_height="100dp"
                android:background="#2196F3" />

            <TextView
                android:layout_width="300dp"
                android:layout_height="300dp"
                android:background="#F44336" />

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:background="#FFC107" />

            <TextView
                android:layout_width="100dp"
                android:layout_height="100dp"
                android:background="#2196F3" />

            <TextView
                android:layout_width="300dp"
                android:layout_height="300dp"
                android:background="#F44336" />

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:background="#FFC107" />

            <TextView
                android:layout_width="100dp"
                android:layout_height="100dp"
                android:background="#2196F3" />

        </LinearLayout>
    </ScrollView>

</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130049385-c1379215-3a3b-486e-8cb1-8dac8d5b744d.png)
![image](https://user-images.githubusercontent.com/86659995/130049430-ac351698-0122-4451-8618-567eac0918a7.png)
