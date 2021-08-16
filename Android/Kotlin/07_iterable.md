# 반복문 (Iterable)
> iterable한 변수를 하나씩 꺼내면서 반복 실행하거나, 조건이 깨질 때까지 실행하는 구문  
> for, while

## for, forEach

### for문 사용방법(1)
```kotlin
for (i in 0..a.size) {  // 0부터 9까지
    println(i)
}
```
```
0
1
2
3
4
5
6
7
8
9
```
> .. 을 사용했을 때에는 .. 뒤에 오는 마지막 수를 포함한다.

---

### for문 사용방법(2)

```kotlin
val a = mutableListOf<Int>(1, 2, 3, 4, 5, 6, 7, 8, 9)

for (item in a) {
        if (item == 5) {
            println("item is Five")
        } else {
            println("item is not Five")
        }
    }
```
```
item is not Five
item is not Five
item is not Five
item is not Five
item is Five
item is not Five
item is not Five
item is not Five
item is not Five
```
item에 리스트 a의 값이 인덱스 순서대로 하나씩 대입된다.

---

### for문 사용방법(3)

배열이나 리스트에서 인덱스와 값을 같이 사용하고 싶을 때

```kotlin
    for ((index, item) in a.withIndex()) {
        println("index : " + index + " value : " + item)
    }
```
> 문자열 + Int(정수) = 문자열  
> 문자열 + 아무거나 = 문자열

---

### for문 사용방법(4) - until
until은 범위에 마지막 숫자를 포함하지 않는다

```kotlin
println(a.size)
println()
for (i in 0 until a.size) {
    // a.size = 리스트 a의 크기 = 9
    // 0 부터 8까지 반복
    println(a.get(i))
    }
```
```
9

1
2
3
4
5
6
7
8
9
```

---

### for문 사용방법(5) - step
해당 숫자만큼 건너뛰기
```kotlin
for (i in 0 until a.size step (2)) {
    println(a.get(i))
}
```
```
1
3
5
7
9
```

---

### for문 사용방법(6) - downTo
역순으로 반복

```kotlin
    for (i in a.size - 1 downTo (0)) {
    // 8(a.size - 1) 부터 0 까지 반복
        println(a.get(i))
    }
```
```
9
8
7
6
5
4
3
2
1
```

---

### for문 사용방법(7) - downTo + step
건너뛰어 내려가기

```kotlin
for (i in a.size - 1 downTo (0) step (2)) { // 2씩 건너뛰며 역순으로 반복
    println(a.get(i)) 
}
```
```
9
7
5
3
1
```

---

### forEach문 사용방법(1) 

```kotlin
a.forEach {
        println(it)
    }
```
> forEach문을 만들면 반복문의 변수명이 자동 지정된다. 
> 바꾸고 싶으면 아래와 같이 코드를 작성한다.

```kotlin
a.forEach { item -> // 변수명을 item으로 변경
        println(item)
    }
```
```
1
2
3
4
5
6
7
8
9
```
변수에 리스트 a의 값들이 순서대로 대입

---

### forEach문 사용방법(2) 

```kotlin
a.forEachIndexed { index, item ->
    println("index : " + index + " value : " + item)
}
```
```
index : 0 value : 1
index : 1 value : 2
index : 2 value : 3
index : 3 value : 4
index : 4 value : 5
index : 5 value : 6
index : 6 value : 7
index : 7 value : 8
index : 8 value : 9
```
forEach문을 통해 배열이나 리스트에서 인덱스와 값을 같이 꺼낸다.

---

## while
### while문 사용방법(1) - while

```kotlin
var b: Int = 0 // -> 1 -> 2 -> 3 -> 4
var c: Int = 4

while (b < c) {
    b++ // while문을 정지 시키시키기 위한 코드
    println("b")
}
var d: Int = 0
var e: Int = 4
```
```
b
b
b
b
```
> 조건식이 맞지않으면 반복문이 한 번도 실행되지 않을 수 있다.

---

### while문 사용방법(1) - do ~ while
조건식과 관계없이 do 블록 안 코드가 무조건 한 번 실행된다. 

```kotlin
var d: Int = 0
var e: Int = 4

do {
    println("hello")
    d++
 } while (d < e)
```
```
hello
hello
hello
hello
```
