# 함수 (Function)
> 어떤 input을 넣어주면 어떤 output이 나오는 것  
> ex) y = x + 2 

## 함수를 선언하는 방법

```kotlin
fun 함수명(변수명: 타입, 변수명: 타입 . . .): 반환형{
	~함수 내용~
	return 반환값
}
```

```kotlin
package Kotlin

fun plus(first : Int, second : Int): Int{
    println(first)
    println(second)
    val result: Int = first + second
    println(result)
    return result
}

fun main(array: Array<String>){
  
    //함수를 호출하는 방법
    val result = plus(5, 10)
    println(result)
    
    // 인수를 명시적으로 전달하는 방법
    val result2 = plus(first = 20, second = 30)
    println(result2)

    val result3 = plus(second = 100, first = 10)
    println(result3)
}
```

```
5
10
15
15

20
30
50
50

10
100
110
110
```

### 디폴트 값을 값는 함수 만들기

```kotlin
fun plusFive(first: Int, secon: Int = 5): Int{
	val result: Int = first + second
	return result
}
```

### 디폴트 값을 갖는 함수 호출하기

```kotlin
val result4 = plusFive(10, 20)
println(result4)

val result5 = plusFive(10)
println(result5)
```

```
30

15
```

### 반환값이 없는 함수 만들기
반환형을 생략하거나 `Unit`을 적어주면 반환값이 없는 함수를 만들 수 있다.

```kotlin
fun printPlus(first: Int, second: Int): Unit{
val result: Int = first + second
println(result)
}

printPlus(10, 20)
```

```
30
```

### 간단하게 함수를 선언하는 방법

```kotlin
fun plusShort(first: Int, second: Int) = first + second

val result6 = plusShort(50, 50)
println(result6)
```

```
100
```

### 가변인자를 갖는 함수 선언하는 방법

```kotlin
fun plusMany(vararg numbers: Int){
	for(number in numbers){
		println(number)
	}
}

plusMany(1, 2, 3)
```

```
1
2
3
```

> 코드 자동정렬 단축키 Ctrl + Alt + L

## 실습

```kotlin
package Kotlin

fun plusThree(first: Int, second: Int, third: Int): Int{
    return first + second + third
}

fun minusThree(first: Int, second: Int, third: Int) = first - second - third

fun multiplyThree(first: Int = 1, second: Int = 1, third: Int = 1): Int {
    return first * second * third
}

// 내부 함수
// 함수 안에 함수가 있다

fun showMyPlus(first: Int, second: Int): Int{
    println(first)
    println(second)

    fun plus(first: Int, second: Int): Int{
        return first + second
    }
    return plus(first, second)
}

fun main(array: Array<String>){
    val result = plusThree(first = 1, second = 2, third = 3)
    println(result)
    val result2 = minusThree(first = 10, second = 1, third = 2)
    println(result2)
    val result3 = multiplyThree(first = 2, second = 2, third = 2)
    println(result3)
    val result4 = multiplyThree()
    println(result4)
    val result5 = showMyPlus(4,5)
    println(result5)
}
```

```
6

7

8

1

4
5
9
```
