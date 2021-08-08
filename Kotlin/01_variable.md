> ### 코틀린이란?  
> ㄴ Jetbrains 에서 개발한 안드로이드 공식 언어
> ### 코틀린이 좋은 이유  
> - 문법이 간결하며, 표현력이 좋다  
> - Null safe 언어이다 (Null 오류가 발생하지 않도록 함)  
> - 기존 라이브러리와 상호운용성이 좋다 (자바와 100% 호환 가능)


# 변수  (Variable)

## 변수 선언 방법
```
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
