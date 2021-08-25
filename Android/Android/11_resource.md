# Resource

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android" android:layout_width="match_parent"
android:layout_height="match_parent">

<TextView
android:layout_width="wrap_content"
android:text="@string/hello"
android:background="@color/textview_color"
android:layout_height="wrap_content" />

<TextView
android:layout_width="wrap_content"
android:background="@color/textview_color"
android:layout_height="wrap_content" />

<TextView
android:layout_width="wrap_content"
android:background="@color/textview_color"
android:layout_height="wrap_content" />

</androidx.constraintlayout.widget.ConstraintLayout>

<resources>
<!-- Base application theme. -->
<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
<!-- Customize your theme here. -->
<item name="colorPrimary">@color/colorPrimary</item>
<item name="colorPrimaryDark">@color/colorPrimaryDark</item>
<item name="colorAccent">@color/colorAccent</item>
</style>

<style name="MyTheme" parent="Theme.AppCompat.Light.DarkActionBar">
<!-- Customize your theme here. -->
<item name="colorPrimary">#ffffff</item>
<item name="colorPrimaryDark">@color/colorPrimaryDark</item>
<item name="colorAccent">@color/colorAccent</item>
<item name="windowNoTitle">true</item>
</style>

</resources>
```

## 실습

```
import kotlinx.android.synthetic.main.activity_listener.*

class Resource : AppCompatActivity(){

override fun onCreate(savedInstanceState: Bundle?){
super.onCreate(savedInstanceState)
setContenView(R.layout.activity_resource)


//1
val ment = resources.getString(R.string.hello)
Log.d("mentt","ment: " + ment)

//2
val ment2 = getString(R.string.hello
Log.d("ment","ment: " + ment2)

//SDK 버전에 따른 분기 처리

/*<LinearLayout
*
* <Button
* android:layout_width="100dp"
* */
val color = if(Build.VERSION.SDK_INT >= Build.VERSION_CODES.M){
button.setBackgroundColor(getColor(R.color.textview_color))
} else{
resources.getColor(R.color.textview_color)
}

button.setBackgroundColor(getColor(R.color.textview_color))
}
}
```
