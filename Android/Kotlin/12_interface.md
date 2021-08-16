# Interface
일종의 구현 약속으로 인터페이스를 구현하는 클래스들은 인터페이스가 가지고 있는 내용을 구현해야한다. 
> 우클릭 > Generate > Implement Methods  

* 상속 : 자식 클래스가 공통으로 가지고 있거나 조금씩만 다른 기능들을 부모 클래스에 올려 놓으면 편하다.  
* 인터페이스 : 인터페이스를 구현하는 클래스들의 기능이 많이 달라도 상관 없다.

인터페이스는 협업할 때 굉장히 유용하다.

## 인터페이스에서 구현되지 않은 함수

```kotlin
interface Person__ {
    fun eat()
    fun sleep()
}

// 인터페이스는 생성자를 빼야 한다
// 인터페이스에 구현되지 않은 함수는 클래스에서 그 함수를 반드시 오버라이딩해서 구현해야 한다. (eat, sleep)
class Student__ : Person__ {
    override fun eat() {
    }

    override fun sleep() {
    }

}
```

## 인터페이스에서 구현된 함수

```
fun main(args: Array<String>){
    val student__ : Student__ = Student__()
    student__.eat()
    student__.sleep()
}

// 인터페이스도 함수를 구현할 수 있다.
// 인터페이스에서 구현된 함수는 클래스에서 그 함수를 구현할 필요가 없다. (eat)
// 이 기능은 반드시 구현 해야한다 : abstract (sleep, study)

interface Person__ {
    fun eat(){
        println("먹는다")
    }
    abstract fun sleep(){
        println("잔다")
    }
    abstract fun study()
}

class Student__ : Person__ {

    //override fun eat() {} 구현할 필요 없음
    
    override fun sleep() {
    }

    override fun study() {
    }

}

class Teacher__ : Person__ {
    override fun sleep() {
    }

    override fun study() {
    }
}
```

> 함수 옆에 { }(중괄호)가 없으면 구현되지 않은 함수이다
