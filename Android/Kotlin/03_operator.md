# 연산자

### 산술 연산자

+, -, *, /(몫), %(나머지)

### 대입 연산자
좌변 = 우변 (우변 값이 좌변에 대입)  
a = 5 (o) 5 = a (x)  
var num = 20 (20이라는 값을 num에 대입)  

### 복합 대입 연산자
+=, -=, *=, /=, %=  
a += 10 > a = a + 10

### 증감 연산자
++, --  
a++, a--

### 비교 연산자
\>, >=, <, <=, ==(같으면 True), !=(다르면 True)  
True == True > True  
True == False > False  
True != True > False  
True != False > True  

### 논리 연산자
&&(AND), ||(OR), !(NOT)  
True && True > True  
True || False > False  
!True > False

## 실습

```kotlin
package Kotlin

fun main(array: Array<String>) {

    //산술 연산자
    var a = 10 + 1
    var b = 10 - 1
    var c= 1 * 9
    var d = 20 / 3
    var e = 20 % 3
    println(a)
    println(b)
    println(c)
    println(d)
    println(e)

    //대입 연산자
    val f = 5

    //복합 대입 연산자
    a += 10
    b -= 10
    c *= 3
    d /= 4
    e %= 2
    println()
    println(a)
    println(b)
    println(c)
    println(d)
    println(e)

    //증감 연산자
    a++
    b--
    println()
    println(a)
    println(b)

    //비교 연산자
    var g = a > b
    var h = a == b
    var i = !h
    var l = i != h
    println()
    println(g)
    println(h)
    println(i)
    println(l)

    //논리 연산자
    var j = h && i
    var k = h || i
    println()
    println(j)
    println(k)
}
```

```
11
9
9
6
2

21
-1
27
1
0

22
-2

true
false
true
true

false
true
```
