# 변수의 접근 범위

변수는 선언된 위치에 따라 접근 범위가 달라진다.
접근 범위에 따라 **전역 변수**와 **지역 변수**로 나눌 수 있다.

**전역 변수** : 함수나 클래스 밖에서 선언된 변수  
**지역 변수** : 함수나 클래스 내에서 선언된 변수

클래스 내에 있는 함수에서는 클래스 멤버 변수에 접근할 수 있지만 main문에서는 접근할 수 없다.  
함수 안에서 선언된 변수도 다른 함수에서 사용할 수 없다.

```kotlin
package Kotlin

var number100: Int = 10 // 전역변수

fun main(args: Array<String>){
    println(number100)
    
    val test = Test("홍길동")
    test.name
    test.testFun()
    println(number100)

}

class Test(var name: String) {
    fun testFun() {
        var birth100: String = "2000/06/05"
        name = "홍길동"
        number100 = 100

        fun testFun2() {
            var gender: String = "Female"
            // 이 함수 안에서만 gender 접근 가능
        }

        // testFun2 함수 밖에선 gender 접근 불가능
    }

        fun testFun3() {
            // name 접근 불가능
            // birth 사용 불가능
        }
    }
```

> 변수의 접근 범위는 최소한으로 설정해야 오류나 의도하지 않은 방향으로 변수를 쓰는 것을 막을 수 있다.

__*메인함수에서 선언된 변수를 클래스의 멤버함수에서 사용할 수 없는지 궁금하다*__
