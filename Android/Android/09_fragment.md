# Fragment

Activity -> 앱에 보이는 한 화면의 단위

* 액티비티가 가지고 있는 문제  
액티비티가 길어지게 되면 관리 포인트가 많아져 관리가 어렵다

* 다양한 디바이스에서 오는 문제
-안드로이드 디바이스가 너무 다양하다
-안드로이드에는 핸드폰만 있는게 아니다 (ex/ 태블릿)

* 사용처
액티비티의 파트를 나누어서 책임진다

### Fragment
* 라이프 사이클이 존재한다
* 액티비티 종속적이다

## 실습

```
<LinearLayout
orientation = "vertical"
<TextView
android: layout_width = "wrap_content"

<LinearLayout
android:layout_width="match_parent"
android:layout_height="200dp"
android:background

<Fragment
android:id = "@+id" // 반드시 id줘야됨
android: layout_width="match_parent"
android: layout_height="300dp"
```

```
import android.os.Bundle
import android.view.LayoutInflater
import androidx.fragment.app.Fragment
import java.util.zip.Inflater

class FragmentOne : Fragment(){

override fun onAttach(context: Context?){
super.onAttach(context)
}
override fun onCreate(savedInstancesState: Bundle?){
super.onCreate(savedInstancesState)
}
override fun onCreateView(
inflater: LayoutInflater,
container: ViewGroup?,
savedInstanceState: Bundle?

): View?{

/*프라그먼트가 인터페이스를 처음으로 그릴때 호출된다
* inflater -> 뷰를 그려주는 역할
* container -> 부모뷰*/

return inflater.inflate(R.layout.fragment_one,container, false)
}
override fun onViewCreated(view: View, savedInstanceState: Bundle?){
super.onViewCreated(view,savedInstanceState)
}

override fun onActivityCreated(savedInstanceState: Bundle?) {
super.onActivityCreated(savedInstanceState)
}

override fun onStart() {
super.onStart()
}

override fun onResume() {
super.onResume()
}

override fun onPause() {
super.onPause()
}

override fun onStop() {
super.onStop()
}

override fun onDestroyView() {
super.onDestroyView()
}

override fun onDetach() {
super.onDetach()
}


}
```
