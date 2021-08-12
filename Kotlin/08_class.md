# 클래스 (Class)

## 객체 지향 프로그래밍 (OOP)
 > OOP - Object Oriented Programing

절차 지향 프로그래밍의 문제 해결 방법  
\- 코드를 위에서 부터 아래로 실행한다

객체 지향 프로그래밍의 문제 해결 방법  
\- 객체를 만들고 객체에게 일을 시켜서 문제를 해결한다

## 클래스 생성
### 클래스 생성 방법(1)
>2번 방법을 축약

```kotlin
class Car constructor(var engine: String, var body: String) {
}
```

### 클래스 생성 방법(2) 
```kotlin
//필수적인 부품 : engine, body
//추가적인 부품: door

class Car1(engine: String, body: String){
    var door: String = "" // 기본값

    constructor(engine: String, body: String, door: String):this(engine, body){
        this.door = door
    }
```
생성자(constructor)가 2개라는 것은 클래스를 만드는 방법이 2개라는 것을 의미한다.
> 1, 2번 방법은 3번 방법을 축약한 것과 같다.

### 클래스 생성 방법(3)
```kotlin
class SuperCar{
    var engine : String
    var body : String
    var door : String = ""

    constructor(engine : String, body: String){
        this.engine = engine // this는 SuperCar 클래스를 의미
        this.body = body
    }
    
    constructor(engine : String, body: String, door:String){
        this.engine = engine 
        this.body = body
        this.door = door
    }
}
```

## 객체 생성
클래스를 통해 객체를 만드는 것을 인스턴스화라고 한다.
> 인스턴스 ≒ 객체

```kotlin
Car("v8 engine", "big")
val bigCar = Car("v8 engine", "big")
```

클래스를 호출하면 생성자가 먼저 호출된다.

```kotlin
val bigCar1: Car = Car("v8 engine", "big")
val superCar: SuperCar = SuperCar("good engine", "big", "white")
```

클래스가 자료형의 역할을 한다. ex) : Car

## 클래스의 기능
클래스의 기능은 클래스의 함수를 통해 만들어진다.

```kotlin
class RunableCar(engine: String, body: String){
    fun ride() {
        println("탑승 하였습니다")
    }
    fun drive(){
        println("달립니다")
    }
    fun navi(destination : String){
        println("$destination으로 목적지가 설정되었습니다")
    }
```

```kotlin
class RunableCar2{
    var engine : String
    var body : String

    constructor(engine: String, body: String){
        this.engine = engine
        this.body = body
    }

    // init - 인스턴스화 될 때 이 부분이 가장 먼저 출력
    // 무조건 호출, 초기 세팅에 유용
    init{
        println("runable2 만들어졌습니다")
    }
    
    fun ride() {
        println("탑승 하였습니다")
    }
    fun drive(){
        println("달립니다")
    }
    fun navi(destination : String){
        println("$destination으로 목적지가 설정되었습니다")
    }
}
``` 
두 클래스의 기능은 완전히 같지만 RunableCar클래스는 engine과 body를 멤버 변수로 갖고 있지 않다.  
`runableCar.engine` 와 같은 코드를 사용할 수 없음.

### 객체가 가지고있는 기능을 사용하는 방법

```kotlin
val runableCar: RunableCar = RunableCar("simple engine", "short body")
runableCar.ride()
runableCar.navi("부산")
runableCar.drive()
```
```
탑승 하였습니다
부산 으로 목적지가 설정되었습니다
달립니다
```

### 객체의 멤버 변수에 접근 하는 방법
```kotlin
val runableCar2: RunableCar2 = RunableCar2("nice engine", "long body")
println(runableCar2.body)
println(runableCar2.engine)
println()
```
```
runable2 만들어졌습니다
long body
nice engine
```
## 오버로딩
> 이름이 같지만 받는 파라미터가 다른 함수  
함수는 이름이 같아도 넣어주는 변수가 다르다면 같은 이름의 함수를 만들 수 있다.

```kotlin
class TestClass(){

    fun test(a:Int){
        println("up")
    }

    fun test(a:Int, b:Int){
        println("down")
    }
}
```
```kotlin
val testCalss = TestClass()
testCalss.test(1)
testCalss.test(1, 2)
}
```
```
up
down
```
