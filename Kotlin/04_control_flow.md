# 제어 흐름

## if, else

```kotlin
package Kotlin

// 08. 제어 흐름
// - if, else
// if문의 조건문은 결괏값이 무조건 True / False로 나와야한다
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

## when

```kotlin
package Kotlin

// 10.제어흐름
// When
// 조건문의 결괏값이 True/False로 나오지 않아도 된다

fun main(args:Array<String>){

    val value: Int = 3

    when (value) {
        1 -> {
            println("value is 1")
        }
        2 -> {
            println("value is 2")
        }
        3 -> {
            println("value is 3")
        }
        else -> {
            println("I don't know value")
        }
    }

    if (value == 1) {
        println("value is 1")
    } else if (value == 2) {
        println("value is 2")
    } else if (value == 3) {
        println("value is 3")
    } else {
        println("I don't know value")
    }

    val value2 =  when(value){
        1 -> 10
        2 -> 20
        3 -> 30
        else -> 100
    }
    println(value2)
}
```

```
value is 3
value is 3
30
```

## 실습

```kotlin
package Kotlin

fun main(args: Array<String>) {

    val value: Int? = null

    when (value) {
        null -> println("value is null")
        else -> println("value is not null")
    }

    val value2: Boolean? = null
    // when 구문은 조건으로 갖는 값의 모든 경우에 대응해주는 것이 좋다
    // value2는 null 을 가질 수 있는 Boolean 형이기 때문에 when 에 null 인 경우도 포함
    when (value2){
        true -> println("")
        false -> println("")
        null -> println("")
    }

    // 값을 리턴하는 when 구문의 경우 반드시 값을 리턴해야한다
    val value3 = when (value2){
        true -> 1
        false -> 3
        null -> 4
    }

    // when 의 다양한 조건식 (1)
    // 자료형 확인
    val value4: Int = 10
    when (value4){
        is Int-> println("value4 is int")
        else -> println("value4 is not int")
    }

    // when 의 다양한 조건식 (2)
    // 숫자 범위
    val value5: Int = 87
    when (value5){
        in 60..70-> println("value5 is in 60-70")
        in 70..80-> println("value5 is in 70-80")
        in 80..90-> println("value5 is in 80-90")
    }
}
```
