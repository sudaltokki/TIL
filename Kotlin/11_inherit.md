# 상속

상속이란 부모 클래스의 기능을 물려받는 것이다.    
클래스마다 똑같은 기능이 부여하고 싶을 때 부모 클래스를 하나 만들어서 자식 클래스가 상속을 받게 할 수 있다.
자식 클래스를 생성할 때 `: 부모클래스명()`을 붙여 상속을 시킬 수 있다.

class는 접근제어자의 기본값이 private이다.  
따라서 상속을 하려면 앞에 open을 붙여 private 속성을 없애줘야한다.  

오버라이딩으로 부모 클래스에 있는 함수의 기능을 확장시켜 사용할 수도 있다.  
function또한 기본적으로 private이 적용되어있기 때문에 open을 붙여주고 오버라이딩을 해야 한다.  
`우클릭` > `Generate` > `Override Methods` 를 눌러 쉽게 작성할 수 있다.

```kotlin
package Kotlin

fun main(args: Array<String>) {

    val superCar100: SuperCar100 = SuperCar100()
    println(superCar100.drive())
    superCar100.stop()

    val bus100: Bus100 = Bus100()
    bus100.drive()

}

// 부모 : Car100
// 자식 : SuperCar100, Bus100

open class Car100() {

    open fun drive(): String {
        return "달린다"
    }

    fun stop() {
    }
}

class SuperCar100() : Car100() { // Car100을 상속받는다

    // 오버라이딩 : 부모의 함수를 덮어쓴다
    override fun drive(): String {
        val run = super.drive() // super : 부모의 클래스. Car100의 drive함수 호출
        return "빨리 $run" // 빨리 달린다
    }
}

class Bus100() : Car100() {

}
```
