# Generic (제너릭)
목적 : 컴파일 시에 타입을 체크해주는 기능  
제너릭은 만들기 어렵고 실제로 만들일이 거의 없기 때문에 사용하는 방법만 숙지한다

```kotlin
fun main(args: Array<String>){

    // <> 꺽쇠에 아무것도 안적으면 제너릭을 사용하지 않은 경우이다
    // 제너릭을 사용하지 않은 경우
    // 형 변환을 해줘야 한다
    val list1 = listOf(1,2,3,"가")
    val b: String = list1[2].toString() // 형 변환 (타입 변환)
    println(b)

    // 제너릭을 사용하는 경우 -> 타입이 안전하다
    val list2 = listOf<String>("a","b","c")
    val c : String = list2[2] // String 이라는 것을 보장 받는다

    // 타입을 체크할 수 없다
    val list3 = listOf(1,2,3,4, "가", 3.0)
    // 강한 타입을 체크 할 수 있다
    val list4 = listOf<Int>(1,2,3,"가") // 강한 타입 체크 (Int가 강한 타입으로 판단됨, "가"를 지워줘야한다)

    // 제너릭을 사용 하지 않은 경우
    val list5 = listOf(1,2,3,"가") // -> Any라는 타입
    // 부모 : Any
    // 자식 : String, Int, Float
}
```
