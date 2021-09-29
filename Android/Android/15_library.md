# Library

### Framework
개발을 하기위해 지켜야하는 틀 ex) 안드로이드 스튜디오  

### Library
- 외부의 도움, 개발을 하기 위해 필요한 도구들이 미리 구현되어 있는 것  
- 함수나, 클래스로 구현되어 있다
- 프레임워크에 없다

### 특징
- 프레임워크에서 하기 힘든 것들을 쉽게 사용할 수 있다
- 프레임워크에서 제공하지 않는 기능을 사용할 수 있다


## 실습

[glide library](http://bumptech.github.io/glide/doc/download-setup.html#proguard) 불러오기
> 라이브러리 관리할때 gradle을 사용하는 것이 좋다.  
직접 jar파일을 다운받아서 사용하면 업데이트할 때마다 파일을 교체해줘야하지만  
gradle을 이용하면 코드를 수정하는 것만으로 업데이트가 가능하다.

링크에 나와있는 대로 gradle 파일을 수정해준다.

### build.gradle (Project: [AppName])

```gradle
repositories {
  mavenCentral()
  maven { url 'https://maven.google.com' }
}
```

### build.gradle (Module: [AppName].app)

```gradle
dependencies {
    implementation 'com.github.bumptech.glide:glide:4.11.0' //compile 명령어 대신 implementation 명령어 사용
    annotationProcessor 'com.github.bumptech.glide:compiler:4.11.0'
}
```

### activity_library.xml
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".LibraryActivity">

    <ImageView
        android:id="@+id/glide"
        android:layout_width="400dp"
        android:layout_height="400dp"/>
</LinearLayout>
```

### LibraryActivity.kt
```
class LibraryActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_library)

        var glide : ImageView = findViewById(R.id.glide)

        Glide.with(this@LibraryActivity) //안에 context, activity, fragment가 들어갈 수 있다
            .load("https://github.com/bumptech/glide/raw/master/static/glide_logo.png")
            .into(glide)
            // 위치를 입력해 glide 생성, load한 것을 into()에 밀어넣는다.
    }
}
```

load할 때 링크를 사용했기 때문에 internet이 연결되어있어야 실행이 가능하다.  
internet을 사용할 수 있도록 manifests파일에 다음 코드를 추가해준다.
```xml
<uses-permission android:name="android.permission.INTERNET" /> 
```

<img src="https://user-images.githubusercontent.com/86659995/135239429-55e9546c-fd89-4db9-a28b-db1cdaf42456.png" width="200" height="400"/>

라이브러리의 추가적인 기능은 자동완성이나 문서를 통해 찾아볼 수 있다.
