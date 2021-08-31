# Fragment (2)

Fragment를 XML에 ViewCompenent로 추가하지 않고 kotlin 코드를 통해 동적으로 작동시키는 방법
> 원할 때 추가하고 없앨 수 있는 것을 동적이라고 한다.

### Transaction
> 작업의 단위

작업의 시작과 끝, 그리고 실행할 일을 적어 특정 작업의 단위를 형성한다.

## 실습 2
FragmentOne 파일과 fragment_one.xml 파일은 동일

### Layout 파일
```xml
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="안녕하세요"
        android:textSize="50dp"></TextView>

    <fragment
        android:id="@+id/fragment_one"
        android:name="com.example.app1.FragmentOne"
        android:layout_width="match_parent"
        android:layout_height="200dp" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="나와라!"/>

<!--    Fragment를 추가하고 싶다면 Linear나 Relative처럼 부모 뷰가 될 수 있는 뷰를 사용해야 한다.-->
<!--    보통 Linear를 가장 많이 사용한다.-->
    <LinearLayout
        android:id="@+id/container"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:orientation="vertical"
        android:background="#61BA64"/>
```

### Activity 파일
```kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_fragment)
        Log.d("life_cycle", "onCreate")

        val button: Button = findViewById(R.id.button)
        button.setOnClickListener {
            // Fragment를 동적으로 작동시키는 방법
            val fragmentOne: FragmentOne = FragmentOne()

            // Fragment를 동적으로 작동시키기 위해선 FragmentManager가 필요하다
            // supportFragmentManager는 AppCompatActivity를 상속받았기 때문에 사용할 수 있는 기능이다
            val fragmentManager = supportFragmentManager

            val fragmentTransaction = fragmentManager.beginTransaction() // Transaction 시작
            // replace를 사용해 View id 자리에 Fragment가 오게 한다
            fragmentTransaction.replace(R.id.container, fragmentOne) // 할 일
            fragmentTransaction.commit() // Transaction 끝
        }
    }
```

* commit() - 시간 될 때 종료 (commitNow와 큰 차이 없지만 commit을 사용하는 게 더 안정적이다)
* commitNow() - 지금 당장 종료
* commitAllowingStateLoss() - 액티비티가 어떤 것을 복구해야할 때 작업단위가 실행되지 않을 수도 있어서 위험

<img src="https://user-images.githubusercontent.com/86659995/131422333-87be8f3c-44dc-4735-943e-d9c939960990.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/131422357-1787bef3-e480-4f7f-b7e5-b2720a883aed.png" width="200" height="400"/>
> 처음에는 LinearLayout을 적용하고 있지만, 버튼을 누르면 Fragment가 작동한다.
