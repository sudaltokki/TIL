# Activity
> 앱의 한 화면  

Activity 클래스는 활동이 상태 변화 (활동 생성, 중단, 재시작, 종료 등)를 알아차릴 수 있는 여러 콜백을 제공합니다.  
(콜백 = 특정한 동작이 발생하게 되면 알려주는 것)

## Life Cycle (수명 주기)

- onCreate
    -> Activity가 만들어질때 단 한번만 호출된다
    -> Activity를 만들 때 단 한번만 하면 되는 작업을 여기에서 해준다
    
- onStart

- onResume
    -> 다시 앱으로 돌아올때 무조건 호출된다
    -> Activity가 다시 호출될 때 하면 되는 작업들을 여기서 해준다

- onPause
    -> 앱의 화면 일부분이 보이지 않을 때

- onStop
    -> 앱의 화면 전부가 보이지 않을 때

- onDestroy

![image](https://user-images.githubusercontent.com/86659995/130346393-029ed027-d838-42e1-90fe-e558cea6d243.png)
> App process killed는 비정상적인 상황이다

참고 - [Android Developers, 활동 수명 주기에 관한 이해](https://developer.android.com/guide/components/activities/activity-lifecycle?hl=ko)

## 실습

`우클릭` > `Generate` > `Override Methods` 통해서 onStart부터 onDestroy 함수를 모두 오버라이딩한다.  
작동을 확인하는 과정에서 **println** 함수보다 **log**를 사용

```kotlin
package com.example.app1

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

//        Log.d를 작성하면 상단에 import android.util.Log라는 코드가 생긴다
//        안드로이드 스튜디오는 auto import를 지원
//        tag는 꼬리표, msg는 나타내고 싶은 message

        Log.d("life_cycle","onCreate")
    }

    override fun onStart() {
        super.onStart()
        Log.d("life_cycle","onStart")
    }

    override fun onResume() {
        super.onResume()
        Log.d("life_cycle","onResume")
    }

    override fun onPause() {
        super.onPause()
        Log.d("life_cycle","onPause")
    }

    override fun onStop() {
        super.onStop()
        Log.d("life_cycle","onStop")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("life_cycle","onDestroy")
    }
}
```
![image](https://user-images.githubusercontent.com/86659995/130347235-cf780434-bee8-405d-98ec-2599ece8602d.png)

에뮬레이터를 실행시키고 하단의 Logcat에 life_cycle을 검색하면 위와 같이 log가 쓰여진 것을 확인할 수 있다.
