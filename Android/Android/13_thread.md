# Thread
> 작업흐름

앱실행 ----> Launcher Activity ---->  작업흐름  
중심이 되는 MainThread가 흘러가는 동안 Launcher Activity나 다른 Activity들이 실행이된다.  

### 안드로이드 MainThrea의 특징
- UI(User Interface) Thread
- 사용자의 input을 받는 쓰레드
- 정지시키거나 종료시키면 더 이상 사용자의 input을 받을 수 없기 때문에 절대 정지시킬 수 없다   
  (App이 crash되기 때문에 하면 안된다)


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


![image](https://user-images.githubusercontent.com/86659995/135127181-5ce77cf3-ffd2-4c55-ab47-1fcd6196f258.png)
![image](https://user-images.githubusercontent.com/86659995/135128480-e843d759-f5f1-47ec-af7f-81677d440186.png)
