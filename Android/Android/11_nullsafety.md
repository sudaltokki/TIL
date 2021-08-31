# Null Safety
> 코틀린의 특징, Null에 대해서 안전하다

### Null vs 0  
**0**: 휴지를 다 쓰고 휴지심만 남은 상태   
**Null** : 휴지심도 없는 상태, 존재하지 않는 상태, 모르는 상태

### Null이 안전하지 않은 이유
**NullPointExceptionError**가 발생한다.

ex)  
0 + 10 = 10  
Null + 10 = ? -> Error  

button.setOnClickListener  
null.setOnClickListener -> Error 

### Null 처리하는 방법
```
if(number != null){
number + 10
}

if(button != null){
button.setOnClickListener
}
```

### 코틀린의 Null Safety는 문법
**?** : Null이 아니라면 이하 구문 실행  
**!!** : Null이 아님을 개발자가 보장한다는 의미


### Null이 될 수 있는 타입
* Int, Double, Float, Class : Null이 될 수 없는 타입
* Int?, Double?, Float?, Class? : Null이 될 수 있는 타입

## 실습 1
```kotlin
class NullSafety : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
       .
       .
       .
        val number : Int = 10
        val number1 : Int? = null

        // val number3 = number? + number1
        val number3 = number1?.plus(number) // plus는 + 역할을 하는 메소드이다
        Log.d("number", "number3 : " + number3)
    }
}
```
![image](https://user-images.githubusercontent.com/86659995/131459899-524e0140-ccd9-4b53-a9e0-ab7d033b4434.png)
number1이 null이기때문에 plus메소드가 실행되지 않고 number3에 number1이 대입되었다.

## 실습 2
```kotlin
class NullSafety : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
       .
       .
       .
        fun plus(a: Int, b: Int?): Int {
            if (b != null) return a + b
            else return a // if문이 모든 경우를 포함해야하기 때문에 else를 적어주지 않으면 에러가 발생한다.
        }

        fun plus2(a: Int, b: Int?): Int? {
            return b?.plus(a) // return 타입을 Int?로 했기때문에 b가 null이어도 에러가 발생하지 않는다.
        }
    }
}
```

## 실습 3
```kotlin
class NullSafety : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
       .
       .
       .
        val number: Int = 10
        val number1: Int? = null
        
        //Null Safety를 위한 도구 : 엘비스 연산자 ( ?: )
        //number1이 null이 아니면 number4에 number1이 대입된다.
        //number1이 null이면 10이 대입된다.
        
        val number4 = number1 ?: 10
        Log.d("number","number4:" + number4)
    }
}
```
![image](https://user-images.githubusercontent.com/86659995/131461102-7ca064da-f0a6-4fb5-ab2a-d1b3110655f7.png)

---

# lateinit
초기화를 나중에 하겠다는 의미
초기값을 세팅하지 않은 상태에서 호출을 하면 에러가 발생한다 (**UninitializedPropertyAccessException**)

init : 초기값 세팅 (initialize)    
late : 나중에  

## 실습
```kotlin
class NullSafety : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
       .
       .
       .
        class Car5(var number: Int){

        }

        lateinit var lateCar: Car5

        lateCar = Car5(10)
        Log.d("number", "late number: " + lateCar.number)
    }
}
```
![image](https://user-images.githubusercontent.com/86659995/131462913-0f9ea62d-9114-44d6-a08e-9363af4893f0.png)

> lateinit은 반드시 나중에 초기화가 되는 것을 확인해야한다.
