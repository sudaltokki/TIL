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

## 실습

```kotlin
package Kotlin

// Night, Monster (부모) -> Charactor
// SuperNight, SuperMonster (자식)

fun main(args:Array<String>){
    val monster = SuperMonster(100, 10)
    val night = SuperNight(130, 8)
    monster.attack(night)
    monster.bite(night)
    // Charactor의 객체가 들어가야하는 자리에 night, 즉 Supernight의 객체가 들어갔는데 오류가 발생하지 않았다.
    // 자식 클래스는 부모 클래스의 타입도 포함한다.
}

// 상속이 만들어낸 특징
// - 자식 클래스는 부모 클래스의 타입
// - 부모 클래스는 자식 클래스의 타입이 아니다!

open class Charator(var hp:Int, val power: Int){

    // 디폴트 값 적어주기 - this.power
    fun attack(charator: Charator, power: Int = this.power){
        charator.defense(power)
    }
    open fun defense(damage:Int) {
        hp -= damage
        // 클래스의 이름 불러오기 javaClass.simpleName
        if (hp > 0) println("${javaClass.simpleName}의 남은 체력 $hp")
        else println("사망 했습니다")
    }
}

// 자식 클래스가 인스턴스화 되기 위해서 부모 클래스 선행되서 인스턴스화 되어야 한다
// 부모 생성자로 넘어갈 애들은 val/var 적지 않아야 함. 부모에 이미 적혀 있음 (이미 지정 됨)

class SuperMonster( hp:Int, power:Int) : Charator(hp, power) {
    fun bite(charator: Charator){
        super.attack(charator, power + 2)
    }
}

class SuperNight(hp: Int, power: Int) : Charator(hp, power) {
    val defensePower = 2
    override fun defense(damage: Int){
        super.defense(damage- defensePower)
    }
}
```
