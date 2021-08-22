# XML 가져오기

Listener라는 새로운 Activity 생성하면 앱의 지도인 `Manifests`에 자동으로 반영된다.  
이 Activity가 사용하는 layout에 다음과 같은 TextView를 만들어주었다.

```xml
    <TextView
        android:id="@+id/hello"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:text="hello"/>
```
이름이 hello인 TextView를 Listener Activity로 가져와보자. 

강의에서 언급하는 방법은 두 가지이다.
1) 직접 찾아서 가져온다.
2) xml을 import해서 가져온다.

```xml
val textView: TextView = findViewById(R.id.hello)
```
1번 방식은 위와 같은 코드를 작성해서 사용할 수 있다.

2번은 함수의 이름을 적으면 자동으로 import되는 형식이었는데 강의와 달리 내 Activity에서는 실행되지 않았다.
> 더이상 지원되지 않는 기능이라고 한다. 사용하고 싶으면 [여기](https://blog.naver.com/oklmg/222154501486)를 참고하면 된다.

강의에서 2번 방식으로 실습하기 때문에 똑같이 코드를 작성하면 오류가 발생한다.  
위의 링크를 통해 2번 기능의 플러그인을 사용하거나 [뷰 결합](https://sudaltokki.tistory.com/9)을 이용하면 된다.  
나는 뷰 결합을 이용해 실습을 진행했다.  

## 실습
```kotlin
package com.example.app1

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import com.example.app1.databinding.ActivityListenerBinding

private lateinit var binding: ActivityListenerBinding

class Listener : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_listener)

        binding = ActivityListenerBinding.inflate(layoutInflater)
        val view = binding.root
        setContentView(view)

        binding.hello.setOnClickListener {
            Log.d("click", "click")
        }
    }
}
```
hello라는 텍스트를 클릭하면 Logcat에 click이라고 뜰 수 있게 코드를 작성했다.   
그 다음 앱을 실행하면 activity_listener.xml을 실행시킬 수 있도록 Manifests에서 launcher가 들어있는 코드를 옮겨준다.  
![tempsnip](https://user-images.githubusercontent.com/86659995/130360043-0027eb62-e2ed-4a37-bd72-d12f064c4c3a.png)

그리고 앱을 실행시키면 activity_listener.xml에 작성한 layout이 보인다.  
그리고 hello를 클릭할 때마다 Log에 click이라고 뜨는 것을 확인할 수 있다.  
![image](https://user-images.githubusercontent.com/86659995/130359952-62205a46-6016-4adf-8372-6ff53c0f5cfd.png)

`OnClickListener`라는 것은 안드로이드에서 사용자의 클릭하는지 듣고 있겠다라는 뜻이다.
여기서 해당하는 View는 TextView인 hello이다.

사용자가 클릭하면 안드로이드 시스템이 listener들을 전부 찾아보고 해당되는 리스너를 호출한다.
이때 클릭된 뷰를 it으로 넘겨준다.

# 익명함수
함수나 클래스에 이름을 붙여주는 것은 나중에 다시 불러오기 위함이다.  
따라서 한 번만 사용하는 함수나 클래스는 이름을 붙여줄 필요가 없다.  

> 뷰 결합 방식으로 작성했더니 강의에서 보여주는 익명함수 방식을 따라하는 것이 어렵다..   
> 나중에 익명함수는 따로 공부해봐야겠다
