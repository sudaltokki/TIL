# Thread
> 작업흐름

앱실행 ----> launcher Activity ---->  작업흐름

### 안드로이드의 쓰레드
->MainThread  
->launcher Activity  
->Activity B  
->영상재생  

### 안드로이드 MainThrea의 특징
- UI(User Interface) Thread
- 사용자의 input을 받는 쓰레드
- 절대 정지시킬 수 없다(하면 안된다)
- 왜냐하면 정지 시키거나 종료 시키면 더 이상 사용자의 input을 받을 수 없기 때문에


## 실습

```
class ThreadActivity : AppCompatActivity(){

override fun onCreate(savedInstanceState: Bundle?){
super.onCreate(savedInstanceState)
setContentView(R.layout.activity_thread)

val thread: Thread = Thread(runnable)


val runnable : Runnable = object : Runnable{
override fun run(){
Log.d("thread-1","Thread is made")
}
}
button.setOnClickListener{
thread.start(

}
Thread(object : Runnable){
override fun run(){
Log.d("thread-1","Thread2 is made")

}
}).start()

Thread(Runnable {
Thread.sleep(2000)
Log.d("thread-1","Thread3 is made")
runOnUiThread {
button.setBackgroundColor(getColor(R.color.textview_color))
}
}).start()


/*<Button
* android: id="@+id/button"
* android: layout_width="100dp"
* android: layout-height="100dp" />*/
}
}
```


