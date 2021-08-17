> ### 코틀린이란?  
> ㄴ Jetbrains 에서 개발한 안드로이드 공식 언어
> ### 코틀린이 좋은 이유  
> - 문법이 간결하며, 표현력이 좋다  
> - Null safe 언어이다 (Null 오류가 발생하지 않도록 함)  
> - 기존 라이브러리와 상호운용성이 좋다 (자바와 100% 호환 가능)

# 변수  (Variable)

## 변수 선언 방법 (1)

```kotlin
var/val 변수명 = 값
```

`var`은 Variable을 의미, 원하는 값을 마음대로 넣을 수 있다   
`val`은 Value를 의미, 값을 한 번 대입하면 바꿀 수 없다

```kotlin
package Kotlin

var num = 10
var hello = "hello"
var point = 3.4
val fix = 20

fun main(args:Array<String>){
    print(num)
}
```

```
10
```
![4](https://user-images.githubusercontent.com/86659995/128623694-38256482-75e9-4822-adc0-e5b77a8c623b.PNG)
> 실행 시 `un main(args:Array<String>){ }`안에 있는 부분이 작동한다.  

> 변수 fix 에 새로운 값을 할당하려고 하면 에러가 발생한다.

# 자료형 (Type)

* 정수형 : Long > Int > Short > Byte
* 실수형 : Double > Float
* 문자 : Char
* 문자열 : String
* 논리형 (True / False) : Boolean 

변수에 한 번 값을 대입하면 그 값에 해당하는 자료형만 사용할 수 있다.

## 변수 선언 방법 (2)

```kotlin
var/val 변수명: 자료형 = 값
```

Kotlin은 자료형을 정해주지 않으면 대입한 값을 보고 자료형을 판단한다.  
> 변수를 선언할 때 자료형을 명시해주는 것을 추천

### Variable or Value?
그렇다면 어느 때 var, val을 써야할까?

1. 변하지 않는 값이라면 **Value**
2. 변동 여부가 확실하지 않을 때는 **Value**

> **Value** 로 선언해놓고 나중에 필요할 때 **Variable** 로 바꾸는 것을 추천

```kotlin
package Kotlin

var number1 : Int = 20
val hello1 : String = "Hello"
val point1 : Double = 3.4
fun main(array: Array<String>){
    number1 = 20
    //number = 20.5 number의 자료형은 정수형이므로 실수를 대입할 수 없다
}
```

# 실습

```kotlin
package Kotlin

var a = 1 + 2 + 3 + 4 + 5 // 연산의 결과값을 변수에 넣어 줄 수 있다.
var b = "1"
var c = b.toInt() // b의 자료형을 정수형으로 변환
var d = b.toFloat() // b의 자료형을 실수형으로 변환

var e = "John"
var f = "My name is $e Nice to meet you"

// Null
//존재하지 않는다
// 자료형 뒤에 ?를 붙여주면 null을 가질 수 있는 자료형이 된다.

//var abc : Int = null 
//Null can not be a value of a non-null type Int
//Null은 non-null 자료형의 값이 될 수 없다.

var abc1 : Int? = null // "null" (x)
var abc2 : Double? = null

var g = a + 3

fun main(array: Array<String>){
    println(a)
    println(b)
    println(c)
    println(d)
    println(f)
    println(abc1)

    println(g)
```

```
1
1
1.0
My name is John Nice to meet you
null
18

```

> 
