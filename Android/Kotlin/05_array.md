# 배열
> 그룹(모음집)이 필요할 때

## 배열을 생성하는 방법

### 배열 생성 방법(1)
> arrayOf<자료형>(값1, 값2, ...)

```kotlin
  val number: Int = 10
    var group1 = arrayOf<Int>(1, 2, 3, 4, 5)
    println(group1 is Array)
```
### 배열 생성 방법(2)
자료형을 정하지 않으면 여러 자료형을 혼합하여 넣을 수 있다.  
> arrayOf(값1, 값2, ...)

```kotlin
    var number1 = 10
    var group2 = arrayOf(1, 2, 3.5, "Hello")
```
```
    true
```

### 배열 생성 방법(3)
> 자료형 지정  
> char -> ' ', string -> " "

```kotlin
    val a1 = intArrayOf(1, 2, 3)
    val a2 = charArrayOf('b', 'c')
    val a3 = doubleArrayOf(1.2, 100.345)
    val a4 = booleanArrayOf(true, false, true)
```

### 배열 생성 방법(4)
> lambda 활용: Array(배열 길이, {값1; 값2; ...})

```kotlin
    var a5 = Array(10, { 0 })
    // 배열의 0~9번 인덱스 모두 0으로 채움
    
    var a6 = Array(5, { 1;2;3;4;5 })
    // lambda에서는 ,(쉼표)가 아닌 ;(세미콜론)으로 값을 구분함
```

## 인덱스 (Index) 
인덱스 = 순서   
인덱스는 0부터 시작한다. 예를 들어 index 0 -> 1, index 1 ->2

### 배열의 값을 꺼내는 방법(1)
```kotlin
    val test1 = group1.get(0)
    val test2 = group1.get(4)
    println(test1)
    println(test2)
```
```
1
5
```

### 배열의 값을 꺼내는 방법(2)
```kotlin
    val test3 = group1[0]
    println(test3)
```
```
1
```



### 배열의 값을 바꾸는 방법(1)

```kotlin
    group1.set(0, 100)
    println(group1[0])
```
```
100
```

### 배열의 값을 바꾸는 방법(2)
```kotlin
    group1[0] = 200
    println(group1[0])
```
```
200
```

## 실습
```kotlin
package Kotlin

fun main(array: Array<String>) {

    val array = arrayOf<Int>(1, 2, 3)

    // get, set
    val number = array.get(0)
    println(number)
    
    array.set(0, 100)
    val number2 = array.get(0)
    println(number2)
    
    //array.set(100, 100)
    //val number1 = array.get(100)
}
```

> 배열의 범위는 처음 만들 때 결정된다. 따라서 인덱스를 사용할 때 결정된 범위를 벗어나지 않도록 주의해야한다.  
> \<Error Message>   
  Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 100 out of bounds for length 3
	at Kotlin._13_PracticeKt.main(13.Practice.kt:17)
