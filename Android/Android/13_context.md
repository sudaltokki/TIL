# Context

**ActivityManagerService**에 접근 하도록 해주는 역할, 주변정보    
> ActivityManagerService는 개발하기 편하도록 미리 구현 해놓은 기능을 말한다.  

안드로이드에 만들어져 있는 많은 기능을 사용하기 위해서는 Context가 필요한 경우가 많다.  
우리가 항상 Activity를 만들때 자동으로 상속받는 AppCompatActivity의 뿌리가 Context이다.

### 종류
* Activity의 context : Activity의 주변정보  
* Application의 context : Application의 주변정보 

### Activity와 Application의 차이는?
manifests를 보면 Application 안에 Activity가 존재한다.   
따라서 Application이 Activity보다 상위에 있고, ApplicationContext가 ActivityContext보다 많은 정보를 담고있다.

Activity와 Application에 대한 정보를 얻기 위해서는 Context를 사용하면 된다.

## 실습

```kotlin
class Context : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        .
        .
        .
        val context : Context = this // this는 이 Context Activity를 의미 , 자식은 부모의 타입이 될 수 있다. 
        val applicationContext = getApplicationContext()
    }
}
```
