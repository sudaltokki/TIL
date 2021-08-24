# Intent
> 의도, 요구, 의사 전달, 요청

### Intent 요청 관계 
- Activity 와 Activity
- Android System과 내 App (ex/전화)
- 다른 App과 내 App (무작정 사용할 수 없다, 상호 합의가 필요)

### 요청의 종류
- 전달만 하는 요청
- 리턴을 받는 요청

### 인텐트의 종류
- 명시적 인텐트 > 정확히 대상에게 요청
- 암시적 인텐트 > 할 수 있는 대상에게 요청, 행동만 명시

#### Context
문맥, Activity가 갖고 있는 주변 정보  
this 와 this@Intent1는 똑같은 의미이고, this만 적어도 무방하지만 **@이하**를 적는것을 추천

#### putExtra()
정보를 담아서 보내는 메서드  
key와 value를 쌍으로 만들어 저장하는 key, value 방식이다. (dictionary)

#### getIntExtra()
받은 정보를 꺼내는 메서드, 자료형을 지정해줘야한다.

## 실습 - 전달만 하는 요청
1. Intent1에서 Intent2로 화면 전환
2. number1과 number2를 Intent2 Activity로 전달
3. Intent2 Activity에서 전달받은 정보를 꺼냄

### \<Intent1\>
  
```kotlin
        val button: Button = findViewById(R.id.change_activity)

        button.setOnClickListener {
            val intent = Intent(this@Intent1, Intent2::class.java) //화면 전환 요청
            
            // apply로 정리해놓는 것이 가독성이 좋다
            intent.apply {
                intent.putExtra("number1", 1)
                intent.putExtra("number2", 2)   
            }
            startActivity(intent) // 요청 전송
        }
```
  
### \<Intent2\>
  
```kotlin
        val number1 = intent.getIntExtra("number1", 0)
        val number2 = intent.getIntExtra("number2", 0)
        // defaultValue 0은 number1을 찾았는데 값이 없을 때 사용한다.

        Log.d("number", "" + number1)
        Log.d("number", "" + number2)
```
  
<img src="https://user-images.githubusercontent.com/86659995/130576771-aa97f66f-f457-495a-85e4-f0d90c406d29.png" width = "200" height = "400"/><img src="https://user-images.githubusercontent.com/86659995/130576802-ea0e02df-2bd1-470f-a829-0f0403728ea9.png" width = "200" height = "400"/>
![image](https://user-images.githubusercontent.com/86659995/130588676-ae7be332-5d8e-4d60-ac6c-2c0f0edcbb48.png)

## 실습 - 전달하고 응답을 받는 요청


### \<Intent1\>
  
```kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent)

        val button: Button = findViewById(R.id.change_activity)

        button.setOnClickListener {
            val intent = Intent(this@Intent1, Intent2::class.java) //화면 전환 요청
            intent.apply {
                intent.putExtra("number1", 1)
                intent.putExtra("number2", 2)
            }
            // 요청 전송
            // 전달만 하는 게 아니라 응답을 받는다
            // requestCode 는 요청을 보내는 intent 들을 구분하는 용도
            startActivityForResult(intent,200)
        }
    }

    override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
        // result를 받는 함수
      
        // requestCode 일치 여부 확인
        if(requestCode == 200) {
            Log.d("number", requestCode.toString())
            Log.d("number", resultCode.toString())
            // result data값 받기
            val result = data?.getIntExtra("result", 0)
            Log.d("number", result.toString())
        }

        super.onActivityResult(requestCode, resultCode, data)
    }
```
  
### \<Intent2\>
  
```kotlin
        val result: Button = findViewById(R.id.result)

        result.setOnClickListener {
            val number1 = intent.getIntExtra("number1", 0)
            val number2 = intent.getIntExtra("number2", 0)

            Log.d("number", "" + number1)
            Log.d("number", "" + number2)

            val res = number1 + number2
            val resultIntent = Intent() // 보낼 요청
            resultIntent.putExtra("result", res)
            setResult(Activity.RESULT_OK, resultIntent) // resultcode를 RESULT_OK (-1)로 설정, resultIntent
            finish() // Activity 종료
        }
```
![image](https://user-images.githubusercontent.com/86659995/130597508-a032ab44-9011-46d2-b245-3df7f9ca9b12.png)

> 너무 어려운데.. 나중에 Intent 다시 공부해야겠다

## 실습 - 암시적 인텐트

```kotlin
        val button: Button = findViewById(R.id.change_activity)

        button.setOnClickListener {
            val intent = Intent(Intent.ACTION_VIEW, Uri.parse("http://m.naver.com"))
            startActivity(intent)
        }
```
<img src="https://user-images.githubusercontent.com/86659995/130576771-aa97f66f-f457-495a-85e4-f0d90c406d29.png" width = "200" height = "400"/><img src="https://user-images.githubusercontent.com/86659995/130599660-bf995551-d6f2-422b-8f84-9dcc81d17156.png" width = "200" height = "400"/>
