# Addview

## List View
> 유사하게 반복되는 뷰를 그리기 위한 도구

### 리스트뷰를 그리는 방법

addView (실제로 리스트뷰를 그리기 위해서 잘 사용되지 않는다)  
->Item을 담을 xml을 만들어 준다  
->그 xml에 내용을 채워준다  
->Container view에 더해준다  
->반복한다

* Listview -> 예전에 많이 사용되었다
* RecycleView -> 최근에 가장 많이 사용이 되고 있고 가장 효율이 높다

## 실습

```
import kotlinx.android.synthetic.main.item_view.view.*

class AddViewActivity : AppCompatActivity() {

override fun onCreate(savedInstanceState: Bundle?) {
super.onCreate(savedInstanceState)
setContentView(R.layout.activity_add_view)

//아이템 리스트 준비
val carList = ArrayList<CarForList>()
for (i in 0 until 10) {
carList.add(CarForList("" + i + "번째 자동차", ""+ i + "순위엔진"))

}

val container = findViewById<LinearLayout>(R.id.addview_container)
val inflater = LayoutInflater.from(this@AddViewActivity)
for(i in 0 until carList.size){

val itemView = inflater.inflate(R.layout.item_view, null)
val carNameView = itemView.findViewById<>(R.id.car_name)
val carEngineView = itemView.findViewById<TextView>(R.id.car_engine)

carNameView.setText(carList.get(i).name)
carEngineView.setText(carList.get(i).engine)
container.addView(itemView)

/*<ScrollView
android:layout_width="match_parent"
android:layout_height="match_parent"
android:fillViewport="true">

<LinearLayout
android:id="@+id/addview_container"
* android:orientation="vertical"
* android:layout_width="match_parent"
* android:layout_height="wrap_content" />*/
}

}
}
class CarForList(val name : String, val engine: String){

}
```

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android" android:layout_width="match_parent"
android:layout_height="match_parent"
android:background="#ffffff"
android:padding="6dp"
android:orientation="vertical">

<LinearLayout
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="horizontal">

<TextView
android:id="@+id/car_name"
android:layout_width="wrap_content"
android:layout_gravity="center"
android:layout_height="wrap_content"
android:padding="6dp"
android:textSize="50dp"/>

<TextView
android:layout_width="1dp"
android:layout_height="match_parent"
android:background="#ffffff" />

<TextView
android:id="@+id/car_engine"
android:layout_gravity="center"
android:textSize="20dp"
android:padding="4dp"
android:layout_width="match_parent"
android:layout_height="wrap_content" />

<LinearLayout
android:layout_width="match_parent"
android:layout_height="1dp"
android:background="#ffffff"/>

</LinearLayout>
<LinearLayout
android:layout_width="match_parent"
android:layout_height="1dp"
android:background="#ffffff" />

</LinearLayout>
```
