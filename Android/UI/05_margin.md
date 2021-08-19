# Margin, Padding

- margin : 해당 view의 바깥쪽 여백
- padding : 해당 view의 안쪽 여백, view의 content가 이동

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_margin="50dp"
        android:background="#FFC107" />

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_margin="50dp"
        android:background="#00BCD4"
        android:paddingLeft="20dp"
        android:paddingTop="40dp"
        android:text="박지원"
        android:textSize="20dp" />

</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130031405-c0aaf9c1-d7b2-48ff-b25d-374a2581f91c.png)
