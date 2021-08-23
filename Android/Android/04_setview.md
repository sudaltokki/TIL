# View를 조작하는 방법

## setText
> 텍스트를 변경하는 함수 

setText를 사용하는 데에는 두 가지 방식이 있다.   
첫 번째는 resid, 즉 resource id를 넣어주는 것이고, 두 번째는 텍스트를 직접 입력하는 것이다.  

이 때 resource id란 resource 폴더의 `strings.xml`에 정의되어있는 string을 말한다.  
이것을 사용할 때에는 전과 같이 `R.id.`을 붙이고 ID를 입력해주면 된다. (여기서 R은 resource를 의미한다.)

밑 코드는 텍스트를 직접 입력하는 방식을 사용하였다.

```kotlin
class Listener : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_listener)

        val hello: TextView = findViewById(R.id.hello)
        
        hello.setText("안녕하세요")
    }
}
```
<img src="https://user-images.githubusercontent.com/86659995/130362410-ffdedfe0-4b3d-4b0b-9992-1cc282d2169f.png" width="200" height="400"/>
                                                                                                                                         
# setImageResource
> 이미지를 변경하는 함수, 이미지의 경로 입력해서 사용

```kotlin

class Listener : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_listener)

        val image1: ImageView = findViewById(R.id.image)
        
        image1.setImageResource(R.drawable.dog)
    }
}

```
gradient 이미지가 dog이미지로 바꾸게 만드는 코드를 작성하였다.

![image](https://user-images.githubusercontent.com/86659995/130462657-54bc50fa-b3c0-4ec1-8bd7-1a8c45bacda2.png)

> 간단하게 Int형을 String으로 바꾸려면 `""+number`와 같이 string을 더해주면 된다.
