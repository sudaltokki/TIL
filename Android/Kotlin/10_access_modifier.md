# 접근 제어자

## private
클래스 내에 선언된 변수를 클래스 외부에서 사용할 수 없도록 만들고 싶다면 변수 앞에 **private**을 붙이면 된다.  

```kotlin
fun main(array: Array<String>) {

    val testAccess: TestAccess = TestAccess("아무개")
    //println(testAccess.name)
    //testAccess.name = "아무개2"
    //println(testAccess.name) // TestAccess 클래스의 멤버 변수인 name에 접근할 수 없다.

}

}

class TestAccess {
    private var name: String = "홍길동"

    constructor(name: String) {
        this.name = name
    }

    fun changeName(newName: String) {
        this.name = newName // 클래스 안에 있는 함수는 name에 접근할 수 있다.
    }
}
```

클래스 안에 있는 함수에도 private을 붙이면 클래스 외부에서 사용할 수 없게 된다.  
주로 내부기능을 보조하거나 공개하고 싶지 않은 함수에 private을 사용한다.

```kotlin

fun main(array: Array<String>) {

    val runningCar: RunningCar = RunningCar()
    runningCar.runFast()
    //runningCar.run() // run 함수에 접근할 수 없다.
}

class RunningCar() {
    fun runFast() {
        run()
    }

    private fun run() { // runFast의 기능을 보조하는 역할
    }
}
```

## 실습
```kotlin
package Kotlin

fun main(array: Array<String>){
    val night = Night(20, 4)
    val monster = Monster(15, 5)
    night.attack(monster)
    monster.attack(night)
}

// 외부에서 매개변수에 접근해서 변경할 수 없게 private를 넣어준다
class Night(private var hp : Int, private var power: Int){
    fun attack(monster: Monster){
        monster.defense(power)
    }

    fun defense(damage:Int) {
        hp -= damage
        if (hp > 0) {
            heal()
            println("기사의 현재 체력은 $hp 입니다")
        }
        else println("기사가 죽었습니다")
    }
    // 클래스 안에서만 쓰게 하려면 private를 쓴다
    private fun heal() {
        // 아무때나 힐을 쓰는 것이 아니라
        // 공격을 당했을 때 죽지 않았다면 힐을 한다
        hp += 3
    }
}



class Monster(var hp:Int, var power:Int){
    fun attack(night: Night) {
        night.defense(power)
    }
    fun defense(damage:Int) {
        hp -= damage
        if (hp > 0) println("몬스터의 현재 체력은 $hp 입니다")
        else println("몬스터가 죽었습니다")
    }
}
```
![image](https://user-images.githubusercontent.com/86659995/129470522-b78ceced-a25b-4069-b0a5-5a391321890e.png)
