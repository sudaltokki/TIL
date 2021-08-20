# Drawable

직접 drawble 파일을 만들 수 있다.
drawble 폴더 우클릭 > Drawable Resource File 눌러서 파일 생성

> layout파일에도 있었던 `xmlns:android="http://schemas.android.com/apk/res/android`  
> 이 코드가 없으면 syntax error 발생  
> `android:layout_width="match_parent"` 와 같은 android 속성을 사용하려면 위 코드가 최상위 뷰에 항상 있어야한다

## gradient, angle, corner
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">

    <!--그라데이션-->
    <gradient
        android:angle="90"
        android:centerColor="#9C27B0"
        android:startColor="#FFC107"
        android:endColor="#2196F3"
        android:gradientRadius="50dp"/>

    <!--모서리를 둥글게 하는 기능-->
    <!--radius = bottomLeftRadius + bottomRightRadius + topLeftRadius +topRightRadius-->
    <corners
        android:radius="50dp"/>

</shape>
```
![image](https://user-images.githubusercontent.com/86659995/130195339-e6613d32-2061-4e28-aad2-b39634e0b7c4.png)

## oval, solid, stroke
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="oval">

    <solid
        android:color="#ffffff"/>

    <stroke
        android:width="20dp"
        android:color="#00BCD4">
        
</shape>
```
![image](https://user-images.githubusercontent.com/86659995/130194566-635b1ebb-4bac-45bb-978b-e9c4d03511ab.png)
