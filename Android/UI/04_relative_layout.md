# Relative Layout
기준을 가지고 상대적으로 뷰의 위치를 정해 줌

- 기준 1 : 부모
- 기준 2: 특정한 뷰

## 부모를 기준으로 배치하는 방법

```xml
<?xml version="1.0" encoding="utf-8"?>

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- parent로 나오는 속성이 부모를 기준으로 움직일 수 있는 속성 -->
    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_centerInParent="true"/>
       <!-- 정 가운데 -->

    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_alignParentBottom="true"/>
        <!-- 왼쪽 아래 -->

    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_alignParentRight="true"/>
        <!-- 오른쪽 위 -->

    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_alignParentLeft="true"/>
        <!-- 왼쪽 위 -->

    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_alignParentStart="true"/>
        <!-- 처음 (왼쪽 위) -->

    <!--    layout_centerHorizontal : 수평의 중심-->
    <TextView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f44336"
        android:layout_centerHorizontal="true"/>
        <!-- 가운데 위-->
</RelativeLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130028186-e970455f-3a4b-4fb1-bbd5-f1af005dcf3e.png)

## 속성 정리
```
  * android:layout_alignParentLeft - 부모(Parent) 영역 내에서 왼쪽(Left)에 배치.

  * android:layout_alignParentTop - 부모(Parent) 영역 내에서 위쪽(Top)에 배치.

  * android:layout_alignParentRight - 부모(Parent) 영역 내에서 오른쪽(Right)에 배치.

  * android:layout_alignParentBottom - 부모(Parent) 영역 내에서 아래쪽(Bottom)에 배치.

  * android:layout_centerHorizontal - 부모(Parent) 영역의 가로(horizontal) 방향 가운데(center) 배치.

  * android:layout_centerVertical - 부모(Parent) 영역의 세로(vertical) 방향 가운데(center) 배치.

  * android:layout_centerInParent - 부모(Parent) 영역의 정 중앙(center)에 배치.

  * android:layout_alignParentStart - 부모(Parent) 영역 내에서 시작 지점(Start)에 배치.

  * android:layout_alignParentEnd - 부모(Parent) 영역 내에서 끝 지점(End)에 배치.
```
## 특정한 뷰를 기준으로 배치하는 방법

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- view1 뷰-->
    <!-- id로 이름 붙이기 -->
    <TextView
        android:id="@+id/view1"
        android:layout_centerInParent="true"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="#f23204"/>

    <!-- 빨간색 뷰의 오른쪽 -->
    <!-- of 뒤에 오는 뷰를 기준으로 움직이는 속성이다-->
    <TextView
        android:id="@+id/view2"
        android:layout_width="50dp"
        android:layout_toRightOf="@+id/view1"
        android:layout_height="50dp"
        android:background="#CDDC39"/>

    <!-- layout_above : 바로 위 -->
    <TextView
        android:id="@+id/view2"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_above="@id/view1"
        android:background="#CDDC39"/>

    <!-- layout_below : 바로 아래 -->
    <TextView
        android:id="@+id/view2"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_below="@id/view1"
        android:background="#CDDC39"/>

    <!-- layout_toLeftof : 바로 아래 -->
    <TextView
        android:id="@+id/view2"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_toLeftOf="@id/view1"
        android:background="#CDDC39"/>

</RelativeLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130028122-3661edf2-6028-46fa-89ca-cd355d231498.png)

## 과제

```xml
<?xml version="1.0" encoding="utf-8"?>

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/one"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_above="@id/five"
        android:layout_toLeftOf="@id/five"
        android:background="#FF9800" />

    <TextView
        android:id="@+id/two"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_above="@id/five"
        android:layout_toLeftOf="@id/three"
        android:background="#3F51B5" />


    <TextView
        android:id="@+id/three"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_above="@id/six"
        android:layout_toRightOf="@id/five"
        android:background="#9C27B0" />

    <TextView
        android:id="@+id/four"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_centerVertical="true"
        android:layout_toLeftOf="@id/five"
        android:background="#FFC107" />

    <TextView
        android:id="@+id/five"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_centerInParent="true"
        android:background="#F44336" />

    <TextView
        android:id="@+id/six"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_centerVertical="true"
        android:layout_toRightOf="@id/five"
        android:background="#E91E63" />

    <TextView
        android:id="@+id/seven"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_below="@id/five"
        android:layout_toLeftOf="@id/eight"
        android:background="#03A9F4" />

    <TextView
        android:id="@+id/eight"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_below="@id/five"
        android:layout_toLeftOf="@id/nine"
        android:background="#009688" />

    <TextView
        android:id="@+id/nine"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:layout_below="@id/six"
        android:layout_toRightOf="@id/five"
        android:background="#CDDC39" />

</RelativeLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130027276-5f90d79e-2a02-4e7e-9ebc-b8ec78a1422a.png)

[참고하면 좋은 블로그](https://blog.naver.com/joymrk/222358824402)
