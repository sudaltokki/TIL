# Thread
> 작업흐름

앱실행 ----> Launcher Activity ---->  작업흐름  
중심이 되는 MainThread가 흘러가는 동안 Launcher Activity나 다른 Activity들이 실행이된다.  

### 안드로이드 MainThread의 특징
- UI(User Interface) Thread
- 사용자의 input을 받는 쓰레드
- 정지시키거나 종료시키면 더 이상 사용자의 input을 받을 수 없기 때문에 절대 정지시킬 수 없다   
  (App이 crash되기 때문에 하면 안된다)

MainThread는 일을 하나씩만 할 수 있기 때문에 여러 가지 일들을 동시에 작동시키려면 새로운 스레드를 만들어야 한다.

## 실습

### ThreadActivity.kt

```kotlin
class ThreadActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_thread)

        val runnable: Runnable = object : Runnable {
            override fun run() {
                Log.d("thread-1", "Thread1 is made")
            }
        } //실행시키고자 하는 일을 Runnable에 담고

        val thread: Thread = Thread(runnable) //Runnable을 Thread에 담아준 후
        val button: Button = findViewById(R.id.button)
        button.setOnClickListener {
            thread.start() //시작 명령어를 통해 Thread를 시작한다.
        }

        Thread(object : Runnable {
            override fun run() {
                Log.d("thread-1", "Thread2 is made")
            }
        }).start()

        Thread(Runnable {
            Log.d("thread-1", "Thread3 is made")
            Thread.sleep(2000) // 스레드 실행 후 2초 쉰다
//            button.setBackgroundColor(getColor(R.color.purple_200)) 
//            UI 관련 부분은 MainThread에서만 변경할 수 있기 때문에 다른 Thread에서 접근하려고하면 에러가 발생한다.
//            이때는 runOnUiThread 이용해서 접근하면 된다.
            runOnUiThread { button.setBackgroundColor(getColor(R.color.purple_200)) } //메인스레드에서 돌아가는 스레드
        }).start() //람다방식


    }
}
```

### activity_thread.xml
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ThreadActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="100dp"
        android:layout_height="100dp"/>
</LinearLayout>
```
<img src="https://user-images.githubusercontent.com/86659995/135128480-e843d759-f5f1-47ec-af7f-81677d440186.png" width="200" height="400"/><img src="https://user-images.githubusercontent.com/86659995/135127181-5ce77cf3-ffd2-4c55-ab47-1fcd6196f258.png" width="800" height="100"/>

버튼을 누를 때마다 "Thread1 is made"라는 log가 찍힌다.  

> Thread는 생성할 일이 거의 없고 관리가 어렵다.  
> 나중에 읽어보기 : [https://hoony-gunputer.tistory.com/entry/kotlinObject-Expression?category=755109](https://hoony-gunputer.tistory.com/entry/kotlinObject-Expression?category=755109)
