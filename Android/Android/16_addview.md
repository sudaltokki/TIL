# Addview

## List View
> 유사하게 반복되는 뷰를 그리기 위한 도구

### 리스트뷰를 그리는 방법

- addView (실제로는 잘 사용되지 않는다)  
Item을 담을 xml을 만들어 준다 -> 그 xml에 내용을 채워준다 -> Container view에 더해준다 ->반복

* Listview -> 예전에 많이 사용
* RecycleView -> 최근에 가장 많이 사용이 되고 있고 가장 효율이 높다

## 실습1 - addView

### activity_add_view.xml
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".AddViewActivity">

    <LinearLayout
        android:id="@+id/addview_container" //itemView를 넣을 container 생성
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
```

### item_view.xml
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#00BCD4"
    android:orientation="vertical"
    android:padding="6dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal">

        <TextView
            android:id="@+id/car_name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:textSize="20dp"
            android:padding="4dp"/>

        <TextView
            android:layout_width="1dp"
            android:layout_height="match_parent"
            android:background="#ffffff" /> //세로 줄

        <TextView
            android:id="@+id/car_engine"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:textSize="20dp"
            android:padding="4dp"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:background="#ffffff"/> //가로 줄

</LinearLayout>
```

### AddViewActivity.kt
```xml
class AddViewActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_add_view)

        //아이템 리스트 준비
        val carList = ArrayList<CarForList>()
        for (i in 0 until 10){
            carList.add(CarForList(""+ i +"번째 자동차", ""+ i + "번째 엔진" ))
        }

        val container = findViewById<LinearLayout>(R.id.addview_container)
        val inflater = this@AddViewActivity.layoutInflater //infalter로 container에 view를 return한다
        for(i in 0 until carList.size){
            val itemView = inflater.inflate(R.layout.item_view, null)
            val carNameView = itemView.findViewById<TextView>(R.id.car_name)
            val carEngineView = itemView.findViewById<TextView>(R.id.car_engine)

            carNameView.setText(carList.get(i).name) //
            carEngineView.setText(carList.get(i).engine)
            container.addView(itemView)

        }
    }
}
class CarForList(val name: String, val engine: String){

}
```
> inflate는 xml에 정의되어있는 view를 실제 객체로 만드는 역할을 한다.

<img src="https://user-images.githubusercontent.com/86659995/135293020-2c27f4a2-fcd2-43f0-90b0-42693da79ac6.png" width="200" height="400"/>

## 실습2 - scrollView

addView는 자동으로 scrollView를 만들어주지 않기 때문에 직접 설정해줘야 한다.

### activity_add_view.xml
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".AddViewActivity">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:fillViewport="true">

        <LinearLayout
            android:id="@+id/addview_container"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical" />
    </ScrollView>
</LinearLayout>
```
<img src="https://user-images.githubusercontent.com/86659995/135295428-7130d891-0872-4a08-a0d6-30249742afb8.png" width="200" height="400"/>
