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

```kotlin
val mNumberList = mutableListOf<Int>(1, 2, 3) // 변경 가능한 List
mNumberList.add(3, 4)
println(mNumberList)

val mNumberSet = mutableSetOf<Int>(1, 2, 3, 4, 4, 4) // 변경 가능한 Set
mNumberSet.add(10)
println(mNumberSet)

val mNumberMap = mutableMapOf<String, Int>("one" to 1) // 변경 가능한 Map
mNumberMap.put("two", 2)
println(mNumberMap)
}

```
[1, 2, 3, 4]
[1, 2, 3, 4, 10]
{one=1, two=2}
```
