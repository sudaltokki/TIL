# Collection
> list, set, map

## List
> 중복 허용
> listOf<자료형>(값1, 값2, ...)

```kotlin
val numberList = listOf<Int>(1, 2, 3, 3)
println(numberList)
println(numberList.get(0))
println(numberList[0])
```
```
[1, 2, 3, 3]
1
1
```

## Set
> 중복 허용X , 순서가 없다  
> 순서가 없기 때문에 인덱스가 없고 get, set 메소드를 사용할 수 없다  
> setOf<자료형>(값1, 값2, ...)
```kotlin
val numberSet = setOf<Int>(1, 2, 3, 3, 3)
numberSet.forEach {
	println(it)
}
```
```
1
2
3
```
## Map 
> Key, Value 방식으로 관리    
> mapOf<자료형, 자료형>(key1 to value1, key2 to value2, ...)
```kotlin
val numberMap = mapOf<String, Int>("one" to 1, "two" to 2)
println(numberMap.get("one"))
```
```
1
```

> List, Set, Map 모두 값을 변경할 수 없다. (Immutable Collections)

## Mutable Collection 
> 값을 변경할 수 있다.  
> mutable컬렉션Of<자료형>(값1, 값2, ...)

### Mutable List
> .add(i, 값), .set(i, 값), .removeAt(i)
 
```kotlin
    val a = mutableListOf<Int>(1, 2, 3)
    a.add(4)
    println(a)
    a.add(0, 100)
    println(a)
    a.set(0, 200)
    println(a)
    a.removeAt(1)
    println(a)
```
```
[1, 2, 3, 4]
[100, 1, 2, 3, 4]
[200, 1, 2, 3, 4]
[200, 2, 3, 4]
```
### Mutable Set
> .add(값), .remove(값)

```kotlin
    val b = mutableSetOf<Int>(1, 2, 3, 4)
    println()
    b.add(2)
    println(b)
    b.remove(2)
    println(b)
    b.remove(100) //없는 값을 삭제해도 에러는 발생하지 않는다.
    println(b)
```
```
[1, 2, 3, 4]
[1, 3, 4]
[1, 3, 4]
```
### Mutable Map
> .put(key, value), .replace(key, value), .clear()
```
    val c = mutableMapOf<String, Int>("one" to 1)
    println()
    c.put("two", 2)
    println(c)
    c.replace("two", 3)
    println(c)
    println(c.keys)
    println(c.values)
    c.clear() // 모든 key와 value들을 지운다
    println(c)
```

```
{one=1, two=2}
{one=1, two=3}
[one, two]
[1, 3]
{}
```
