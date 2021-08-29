# Fragment

액티비티의 파트를 나누어서 책임짐으로써 아래 두 가지 문제를 해결할 수 있다.

1. 액티비티가 가지고 있는 문제  
  액티비티가 길어지게 되면 관리 포인트가 많아져 관리가 어렵다.

2. 다양한 디바이스에서 오는 문제  
  안드로이드에는 태블릿 등 다양한 디바이스가 있어서 한 액티비티로 관리하기 어렵다.

####  특징
* Fragment에도 라이프 사이클이 존재한다
* Fragment의 라이프 사이클은 액티비티 종속적이다

## 실습

<액티비티로 파트를 나눌 때>
```xml
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="안녕하세요"
        android:textSize="50dp">
    </TextView>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:background="@drawable/gradient"/>
```
<img src="https://user-images.githubusercontent.com/86659995/131253112-0d8295fe-cc74-464d-b01c-5ec5bd41c5c2.png" width="200" height="400"/>

<Fragment로 파트를 나눌 때>
com.example.app1에 Activity 'FragmentAvtivity'와 kotlin file 'FragmentOne' 생성
