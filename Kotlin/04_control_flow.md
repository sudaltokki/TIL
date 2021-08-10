# 제어 흐름

```kotlin
package Kotlin

// 08. 제어 흐름
// - if, else
fun main(args: Array<String>) {
    val a: Int = 5
    val b: Int = 10

    // if/else 사용하는 방법 (1)
    if (a > b) {
        println("a가 b보다 크다")
    } else {
        println("a가 b보다 작다")
    }

    // else없이 if 사용하는 방법 (2)
    if (a > b) {
        println("a가 b보다 크다")
    }

    //if/else/else if 사용하는 방법 (3)
    if (a > b) {
        println("a가 b보다 크다")
    } else if(a < b){
        println("a가 b보다 작다")
    } else if(a == b){
        println("a와 b는 같다")
    } else {

    }

    // 값을 리턴하는 if 사용하는 방법 (1)
    val max = if(a > b) {
        a //5
    } else {
        b //10
    }

    // 값을 리턴하는 if 사용하는 방법 (2)
    val max1 = if(a > b) a else b
    
    println()
    println(max)
}
```

```
a가 b보다 작다
a가 b보다 작다

10
```

## 실습

```kotlin
package Kotlin

fun main(args:Array<String>) {

    val a: Int? = null
    val b: Int = 10
    val c: Int = 100

    if (a == null) {
        println("a is null")
    } else {
        println("a is not null")
    }

    if (b + c == 110) {
        println("b plus c is 110")
    } else {
        println("b plus c is not 110")
    }

    // 엘비스 연산자 (null safe)
    val number1: Int? = null
    val number2 = number1 ?: 10
    // number2에 number1을 대입, 하지만 number1이 null이면 10을 대입
    println()
    println(number2)

    // 값을 리턴하는 if
    val num1: Int = 10
    val num2: Int = 20
    val max = if(num1 > num2) {
        num1 //10
    } else if(num1 < num2) {
        num2 //20
    } else {
        100
    }
}
```
