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
