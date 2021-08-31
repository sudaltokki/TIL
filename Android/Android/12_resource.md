# Resource

`color.xml`에서는 color code를 관리한다.  

`strings.xml`에서는 긴 문자열이나 고유한 문자열을 관리한다.  

`styles.xml`에서는 Theme를 관리한다.  
 ㄴ**windowNoTitle** 속성을 사용하면 상단에 앱 이름이 나오는 부분이 사라진다.

## 실습 1
```kotlin
class Resource : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_resource)

        // String을 가져오는 방법 1
        // AppCompatActivity를 상속받기 때문에 resources를 사용할 수 있다.
        val ment = resources.getString(R.string.string1) // string은 resource 타입
        Log.d("resource","ment: "+ ment)

        // String을 가져오는 방법 2
        val ment2 = getString(R.string.string1)
        Log.d("resource","ment2: "+ ment)
    }
}
```
## 실습 2

### Layout 파일
```xml
  .
  .
  .
    <TextView
        android:layout_width="match_parent"
        android:layout_height="300dp"
        android:background="#00BCD4"/>
  .
  .
  .
```

### Activity 파일
```kotlin
class Resource : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_resource)
        
        // Color를 가져오는 방법 - SDK 버전에 따른 분기 처리
        val color = if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
            getColor(R.color.purple_200)
            
        } else {
            TODO("VERSION.SDK_INT < M")
        }

        Log.d("resource","color: "+ color)
        
        // TextView의 배경색을 바꾼다.
        val text_view : TextView = findViewById(R.id.text_view)
        text_view.setBackgroundColor(getColor(color))
    }
}
```
<img src="https://user-images.githubusercontent.com/86659995/131470413-e6c59eea-e674-417f-8f50-66ddb0ab30c1.png" width="200" height="400"><img src="https://user-images.githubusercontent.com/86659995/131470319-0a811619-cffe-4df3-a6e9-12f2f394419e.png" width="200" height="400">

> getColor 메소드는 API23부터 deprecated 되었다. 
