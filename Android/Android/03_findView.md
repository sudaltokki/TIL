# XML 가져오기

Listener라는 새로운 Activity 생성하면 앱의 지도인 `Manifests`에 자동으로 반영된다.  
이 Activity가 사용하는 layout에 다음과 같은 TextView를 만들어주었다.

```xml
    <TextView
        android:id="@+id/hello"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:text="hello"/>
```
이름이 hello인 TextView를 Listener Activity로 가져와보자. 

강의에서 언급하는 방법은 두 가지이다.
1) 직접 찾아서 가져온다.
2) xml을 import해서 가져온다.

```xml
val textView: TextView = findViewById(R.id.hello)
```
1번 방식은 위와 같은 코드를 작성해서 사용할 수 있다.

2번은 함수의 이름을 적으면 자동으로 import되는 형식이었는데 강의와 달리 내 Activity에서는 실행되지 않았다.
> 더이상 지원되지 않는 기능이라고 한다. 사용하고 싶으면 [여기](https://blog.naver.com/oklmg/222154501486)를 참고하면 된다.

# 익명함수
함수나 클래스에 이름을 붙여주는 것은 나중에 다시 불러오기 위함이다.  
따라서 한 번만 사용하는 함수나 클래스는 이름을 붙여줄 필요가 없다.  
