# Library

### Framework
안드로이드 스튜디오  
개발을 하기위해 지켜야하는 틀

### Library
외부의 도움, 개발을 하기 위해 필요한 도구들이 미리 구현되어 있는 것  
함수나, 클래스로 구현  
프레임워크에 없다

### 특징
- 프레임워크에서 하기 힘든 것들을 쉽게 사용할 수 있도록 만들어 놨다
- 프레임워크에서 제공하지 않는 기능을 사용할 수 있도록 만들어 놨다


## 실습

```
<LinearLayout

 <ImageView
 android:is="@+id/glide"
 android:layout_width="300dp"
 android:layout_height="300dp" />

 <ImageView
 android:is="@+id/glide2"
 android:layout_width="300dp"
 android:layout_height="300dp" />
```

```
class LibraryActivity : AppCopatActivity(){

override fun onCreate(savedInstanceState: Bundle?){
super.onCreate(savedInstanceState)
setContentView(R.layout.activity_library)

Glide.with(this@LibraryActivity)
.load("")
.fitCenter()
.ceterCrop()
.into(glide)

Glide.with(this@LibraryActivity)
.load("")
.fitCenter()
.into(glide2)
}
}


apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'

android {
compileSdkVersion 30
buildToolsVersion "30.0.2"

defaultConfig {
applicationId "com.example.fastcampus"
minSdkVersion 16
targetSdkVersion 30
versionCode 1
versionName "1.0"

testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
}

buildTypes {
release {
minifyEnabled false
proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
}
}
}

dependencies {
implementation fileTree(dir: "libs", include: ["*.jar"])
implementation "org.jetbrains.kotlin:kotlin-stdlib:$kotlin_version"
implementation 'androidx.core:core-ktx:1.1.0'
implementation 'androidx.appcompat:appcompat:1.1.0'
implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
testImplementation 'junit:junit:4.12'
androidTestImplementation 'androidx.test.ext:junit:1.1.1'
androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'

implementation 'com.github.bumptech.glide:glide:4.11.0'
// Skip this if you don't want to use integration libraries or configure Glide.
annotationProcessor 'com.github.bumptech.glide:compiler:4.11.0'
}
```
