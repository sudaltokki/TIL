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
