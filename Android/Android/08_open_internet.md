# 과제 - 인터넷 페이지 열기

1. EditText, hint 속성 사용
2. Button을 누르면 EditText에 적힌 링크로 이동
3. addTextChangedListener를 이용해 EditText에 적히는 글자들을 감지

## Activity 파일
```kotlin
 override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_open_internet)

        val address: EditText = findViewById(R.id.address)
        val button: Button = findViewById(R.id.button)


        button.setOnClickListener {
            var address = address.text.toString()
            val intent = Intent(Intent.ACTION_VIEW, Uri.parse(address))
            startActivity(intent)
        }

        // EditText의 변화를 감지하는 함수 (익명함수방식)
        address.addTextChangedListener (object : TextWatcher{
            override fun beforeTextChanged(p0: CharSequence?, p1: Int, p2: Int, p3: Int) {
                Log.d("edit", "beforeTextChanged: "+p0)
            }

            override fun onTextChanged(p0: CharSequence?, p1: Int, p2: Int, p3: Int) {
                Log.d("edit", "onTextChanged: "+p0)

            }

            override fun afterTextChanged(p0: Editable?) {
                if(p0.toString() == "abc"){
                    Log.d("edit", "text is abc")
                }
                Log.d("edit", "afterTextChanged: "+p0)
            }
        })
    }
```

## Layout 파일
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".OpenInternet"
    android:orientation="vertical"
    android:gravity="center_horizontal">

    <EditText
        android:id="@+id/address"
        android:layout_marginTop="100dp"
        android:layout_width="370dp"
        android:layout_height="70dp"
        android:hint="인터넷 주소를 입력해 주세요" />

    <Button
        android:id="@+id/button"
        android:layout_width="370dp"
        android:layout_height="50dp"
        android:text="인터넷 페이지 열기"/>

</LinearLayout>
```

<img src="https://user-images.githubusercontent.com/86659995/130761368-890395ee-3dbb-43b5-82e7-9eaf500c6109.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/130761414-e5f02626-f953-40b1-bad5-2fea2afe8b89.png" width="200" height="400"/>  
> 버튼을 눌러 링크로 이동
<img src="https://user-images.githubusercontent.com/86659995/130761224-8bdffee6-c9e2-41a9-afb3-c4d3e8f39eac.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/130761256-4bced601-affb-41d6-bfc9-cfdff4e03faf.png" width="600" height="200"/>
> Logcat을 통해 EditText의 변화를 감지하는 함수의 작동을 확인
