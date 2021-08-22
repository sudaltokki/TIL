# 안드로이드 스튜디오 투어

## Manifests
> 앱의 지도 역할, 어떤 화면이 있는지 어떤 기능을 하는지 나타낸다.  

![image](https://user-images.githubusercontent.com/86659995/130260079-eb796c82-fc26-444a-99f9-0821500d1613.png)

#### package
앱의 이름, 앱을 구분하는 용도로 쓰이기때문에 패키지명은 고유해야 한다.

#### \<application>~\</application>
앱에 대한 내용들을 적어놓는 곳

#### allowBackup
true로 설정해놓으면 앱을 삭제하더라도 지정된 내용들은 저장되어 재설치시 복구된다.

#### label 
앱 이름

#### roundIcon
휴대폰마다 앱을 그리는 모양이 다른데 둥근 모양을 그릴 때 이 이미지를 참조한다

#### supportRrl
글을 오른쪽에서 왼쪽으로 읽는 지역에서 사용된다, right to left

#### theme
style은 앱의 기본값들을 모아놓은 것이다

#### launcher
activity를 런처(앱을 켜자마자 나오는 화면)로 만들어주는 속성

## Java
![image](https://user-images.githubusercontent.com/86659995/130342803-79cc4b62-75b3-4531-b098-aea79ffd6c61.png)

`com.example.app_name` 중에서도 맨 위 폴더는 앱을 만들 때 사용, 밑 두 개는 테스트할 때 사용   
`java (generated)` 폴더는 안드로이드 스튜디오가 자동으로 생성하는 파일을 저장하는 곳

## res (resource)
![image](https://user-images.githubusercontent.com/86659995/130344279-4d510a1e-0502-4021-973a-f21d82b5409a.png)

#### drawable
앱에서 사용되는 이미지가 저장되는 곳

#### layout
화면을 그릴때 사용되는 파일들이 모여있는 곳

#### mipmap
앱의 아이콘이 저장되는 곳

#### values
변수들이 저장되어 있는 곳
`colors.xml` 는 컬러 코드를 저장하는 곳, **@color** 를 입력해 사용할 수 있음  
`strings.xml`는 반복되거나 긴 문자열을 저장하는 곳  
`themes.xml` 파일을 보면 다음과 style을 정의하거나 color 이름을 변수로 저장한다.

```xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.App1" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item> 
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>
```
`res (generated)` 도 마찬가지로 자동으로 저장되는 파일들이 모여있는 곳

## Gradle Scripts
![image](https://user-images.githubusercontent.com/86659995/130344254-ee7cec67-5173-4d43-8370-e4e3c5a1d39c.png)

`build.gradle` 은 gradle이란 언어로 작성됨

#### `build.gradle(Project)` 는 프로젝트에 있는 모든 앱들에 적용  
* repositories - 저장소

* dependencies - 의존성
프로젝트가 만들어질 때 여기에 쓰여진 것을 참조한다

#### `build.gradle(Modul.app)`는 특정 앱에만 적용, 더 적용되는 범위가 좁다

* plugin 
추가적인 기능

* complieSdkVersion - gradle은 컴파일하는 기능을 갖고있음, 이때 컴파일하는 API 버전

* applicationId - 패키지명 (고유해야 한다)

* minSdkVersion - 앱을 구동할 때 최소로 설치되어있어야 되는 버전

* targetSdkVersion = compileSdkVersion

* versionCode - 앱의 버전 (숫자), 업데이트될때마다 하나씩 올라간다

* versionName - 앱의 버전 (이름)

* testInstrumnetationRunner - 테스트코드를 실행할 수 있는 것

* buildTypes - release = 배포 목적

#### proguard-rules
보안을 위해 코드를 난독화 시키는 것

#### settings.gradle
앱을 추가로 만들 때 자동으로 수정된다.

> 그 외 `gradle-wrapper.properties`, `gradle.properties`, `local.properties`은 사용하지 않는다.

## 그 외 기능

* 안드로이드 스튜디오는 실시간 저장이 되기 때문에 저장 버튼을 누르지 않아도 된다

![2021-08-22 (6)](https://user-images.githubusercontent.com/86659995/130344814-e2389e17-ce5e-4980-9b61-0a4b3a5f07d7.png)  
파일 정렬 기준이 달라진다. 보통 Android로 놓고 사용

![image](https://user-images.githubusercontent.com/86659995/130344908-f7a28c54-3193-4669-ba83-53eab1413db8.png)  

* Debug (벌레 모양 버튼) - 문제가 되는 부분을 확인할 때 사용, 숫자 옆을 클릭하면 생기는 빨간 기호까지만 실행시킨다

![2021-08-22 (7)](https://user-images.githubusercontent.com/86659995/130345044-75e38ece-b86e-48a7-824e-6015af229c37.png)  
portrait -  세로 모드, landscape  - 가로 모드

* `Shift`를 두 번 연타하면 파일을 검색, `Ctrl`+`Shift`+`F`를 누르면 코드 안 글자를 검색

![image](https://user-images.githubusercontent.com/86659995/130345145-ade0959a-3e35-47cf-960a-a75d0b63ed10.png)  

* keymap - 단축키 관리  
* Font - 글씨 폰트도 설정 가능하지만 추천하지 않음  
* Color Scheme - 코드의 가독성을 위해 색깔을 지정  

![2021-08-22 (8)](https://user-images.githubusercontent.com/86659995/130345269-5164cc05-b6ab-4ed0-ad89-3e3a8a68e271.png)

안드로이드 스튜디오 재설치시, 기존 세팅을 그대로 가져가고 싶을 때 사용

`[File]` > `[Manage IDE Settings]` > `[Export Settings]`  
기존에 설정된 내용들이 `settings.zip` 이라는 파일로 만들어진다

`[File]` > `[Manage IDE Settings]` > `[Import Settings]`  
다운받은 파일을 새로 설치한 안드로이드 스튜디오에 불러온다.

