# Fragment (1)

액티비티의 파트를 나누어서 책임짐으로써 아래 두 가지 문제를 해결할 수 있다.

1. 액티비티가 가지고 있는 문제  
  액티비티가 길어지게 되면 관리 포인트가 많아져 관리가 어렵다.

2. 다양한 디바이스에서 오는 문제  
  안드로이드에는 태블릿 등 다양한 디바이스가 있어서 한 액티비티로 관리하기 어렵다.

####  특징
* Fragment에도 라이프 사이클이 존재한다
* Fragment의 라이프 사이클은 액티비티 종속적이다

## 실습 1

#### Activity 파일
```kotlin
class FragmentActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_fragment)
        Log.d("life_cycle", "onCreate")
    }

    override fun onStart() {
        super.onStart()
        Log.d("life_cycle", "onStart")
    }

    override fun onResume() {
        super.onResume()
        Log.d("life_cycle", "onResume")
    }

    override fun onPause() {
        super.onPause()
        Log.d("life_cycle", "onPause")
    }

    override fun onStop() {
        super.onStop()
        Log.d("life_cycle", "onStop")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("life_cycle", "onDestroy")
    }
}
```

### <Layout로 파트를 나누는 경우>
#### Layout 파일
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

### <Fragment로 파트를 나누는 경우>
com.example.app1에 Activity 'FragmentAvtivity'와 kotlin file 'FragmentOne' 생성

#### Layout 파일
```xml
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="안녕하세요"
        android:textSize="50dp"></TextView>

<!--    Fragment는 id를 무조건 지정해줘야 한다.-->
<!--    name으로 이 컴포넌트를 어떤 Fragment가 차지할 것인지 써준다-->
    <fragment
        android:id="@+id/fragment_one"
        android:name="com.example.app1.FragmentOne"
        android:layout_width="match_parent"
        android:layout_height="200dp" />
```

#### FragmentOne 파일
> 위 Fragment 컴포넌트를 차지한다.

```kotlin
class FragmentOne: Fragment() { // Fragment는 상속을 통해 사용할 수 있다.
    override fun onAttach(context: Context) {
        Log.d("life_cycle", "F onAttach")
        super.onAttach(context)
    }

    override fun onCreate(savedInstanceState: Bundle?) {
        Log.d("life_cycle", "F onCreate")
        super.onCreate(savedInstanceState)
    }

    // onCreateView - Fragment가 인터페이스를 처음으로 그릴 때 호출되는 라이프 사이클
    // Activity 라이프 사이클의 onCreate와 다르다
    // savedInstanceState 외에 inflater와 container가 추가적으로 들어옴
    override fun onCreateView(
        inflater: LayoutInflater, // layout을 그린다
        container: ViewGroup?, // fragment 컴포넌트의 부모 뷰, 어디에 그릴 지 설정
        savedInstanceState: Bundle?
    ): View? {
        Log.d("life_cycle", "F onCreateView")

        // R.layout에 있는 fragment_one.xml 파일을 불러와 container에 그릴 것이다
        // 뷰를 그릴때 어떤 resource를 쓸 것인지 결정
        return inflater.inflate(R.layout.fragment_one,container, false)
        // inflate 메서드는 결과적으로 View를 return한다
    }

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        Log.d("life_cycle", "F onViewCreated")
        super.onViewCreated(view, savedInstanceState)
    }

    override fun onActivityCreated(savedInstanceState: Bundle?) {
        Log.d("life_cycle", "F onActivityCreated")
        super.onActivityCreated(savedInstanceState)
    }

    override fun onStart() {
        Log.d("life_cycle", "F onStart")
        super.onStart()
    }

    override fun onResume() {
        Log.d("life_cycle", "F onResume")
        super.onResume()
    }

    override fun onPause() {
        Log.d("life_cycle", "F onPause")
        super.onPause()
    }

    override fun onStop() {
        Log.d("life_cycle", "F onStop")
        super.onStop()
    }

    override fun onDestroyView() {
        Log.d("life_cycle", "F onDestroyView")
        super.onDestroyView()
    }

    override fun onDetach() {
        Log.d("life_cycle", "F onDetach")
        super.onDetach()
    }
}
```

#### fragment_one.xml 파일
> FragmentOne이라는 Fragment가 그릴 layout

```xml
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#009688"> // 배경 색만 지정

</androidx.constraintlayout.widget.ConstraintLayout>
```

<img src="https://user-images.githubusercontent.com/86659995/131353708-14d26331-7656-4f2b-b5da-33a6fae19cfe.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/131358494-f57938a0-db05-48f8-8fa1-e725a88d25ae.png" width="600" height="200"/>

Activity의 OnCreate보다 Fragment의 라이프 사이클 4개가 먼저 호출되었다.  
Fragment를 사용하게 되면 라이프 사이클이 복잡해진다.  
하지만 라이프 사이클을 변경할 일이 많지 않기 때문에, 단점보다 장점이 더 많다.
