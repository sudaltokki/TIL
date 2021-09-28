# Fragment (2)

Fragment를 XML에 ViewCompenent로 추가하지 않고 kotlin 코드를 통해 동적으로 작동시키는 방법
> 원할 때 추가하고 없앨 수 있는 것을 동적이라고 한다.

### Fragment 작동 관련 메소드
**<Fragment를 작동시킬 때 사용하는 메소드>**
* replace
* add  

둘은 거의 동일하다.

**<Fragment를 제거할 때 사용하는 메소드>**
* detach  - 다시 작동이 불가능하다
* remove - 다시 작동 가능하다

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

## 실습 3 - 1

### Activity 파일
```kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_fragment)
        Log.d("life_cycle", "onCreate")

        // button2에서도 이 Fragment에 접근할 수 있도록 함수 밖에서 선언해준다.
        val fragmentOne: FragmentOne = FragmentOne()

        val bundle: Bundle = Bundle()
        bundle.putString("hello", "hello")
        fragmentOne.arguments = bundle

        val button: Button = findViewById(R.id.button)
        button.setOnClickListener {

            val fragmentManager = supportFragmentManager

            val fragmentTransaction = fragmentManager.beginTransaction()
            fragmentTransaction.replace(R.id.container, fragmentOne)
            fragmentTransaction.commit()
        }

        val button2: Button = findViewById(R.id.button2)
        button2.setOnClickListener {
            val fragmentManager = supportFragmentManager
            val fragmentTransaction = fragmentManager.beginTransaction() // Transaction 시작
            fragmentTransaction.detach(fragmentOne) // 할 일 : Fragment 제거
            fragmentTransaction.commit() // Transaction 끝
        }
    }
```
>  '나와라' 버튼을 누르면 Fragment가 작동되고, '사라져' 버튼을 누르면 Fragment가 제거된다.

<img src="https://user-images.githubusercontent.com/86659995/131429839-79a09ce4-d9aa-416b-aab4-668c5a06c3ac.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/131429866-7d910983-3cad-4ea7-a0f4-9f35f37e4648.png" width="200" height="400"/>

## 실습 3 - 2 Activity에서 Fragment로 데이터 보내기

### Activity 파일
```kotlin
.
.
.
        // button2에서도 이 Fragment에 접근할 수 있도록 함수 밖에서 선언해준다.
        val fragmentOne: FragmentOne = FragmentOne()

        // Fragment에 data를 넣어주는 방법
        // bundle을 만들어 데이터를 입력하고 Fragment의 arguments에 bundle을 할당해준다.
        val bundle: Bundle = Bundle()
        bundle.putString("hello", "hello")
        fragmentOne.arguments = bundle
 .
 .
 .

```

### FragmentOne 파일

```kotlin
.
.
.
    override fun onActivityCreated(savedInstanceState: Bundle?) {
        Log.d("life_cycle", "F onActivityCreated")

        val data = arguments?.getString("hello")
        Log.d("data", "" + data)


        super.onActivityCreated(savedInstanceState)
    }
.
.
.
```
![image](https://user-images.githubusercontent.com/86659995/131429471-ce9d677c-fe4e-461f-b8b3-ecd63e361d95.png)

데이터는 함수 밖에서 입력해 Fragment에 넣어줬지만,   
transaction이 함수 안에서 실행되기 때문에 데이터가 들어가있는 Fragment도 여기서 처음 실행된다. 

## 실습 4 Fragment에서 Activity로 데이터 보내기
> layout 파일에서 fragment 컴포넌트를 주석처리하고 진행하였다.

### FragmentOne 파일
```kotlin
class FragmentOne : Fragment() { // Fragment는 상속을 통해 사용할 수 있다.

    // 인터페이스를 꼭 여기에 만들지 않아도 된다.
    interface OnDataPassListener {
        fun onDataPass(data: String?)
    }

    lateinit var dataPassListener: OnDataPassListener

    override fun onAttach(context: Context) {
        Log.d("life_cycle", "F onAttach")
        super.onAttach(context) // context : 어플리케이션이나 객체의 현재 상태를 나타내주는 역할
        dataPassListener = context as OnDataPassListener  // context를 OnDataPassListener로 형변환
    }

    .
    .
    .
    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        Log.d("life_cycle", "F onViewCreated")
        super.onViewCreated(view, savedInstanceState)

        // Activity의 onCreate에서 했던 작업을 Fragment에선 onViewCreated에서 한다.
        val pass: Button = view.findViewById(R.id.pass)
        pass.setOnClickListener {
            dataPassListener.onDataPass("Good Bye") // data를 보낸다
        }
    }
    .
    .
    .
}
```

### Activity 파일
```kotlin
class FragmentActivity : AppCompatActivity(), FragmentOne.OnDataPassListener {

    // data를 받는다
    override fun onDataPass(data: String?) {
        Log.d("pass", ""+data)
    }
    .
    .
    .
}
```
![image](https://user-images.githubusercontent.com/86659995/131456418-7fe9c729-e172-4202-b214-c2baaff619c5.png)

Fragment에서는 findViewById를 바로 사용할 수 없다는 사실을 알게 되었다.  
검색을 통해 view.을 붙여 해결하기는 했지만 View class가 어떤 역할을 하는지 잘 모르겠다. (나중에 보충)
