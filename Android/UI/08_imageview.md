# Image View

저해상도 핸드폰은 고해상도 이미지를 그리는 데 시간이 오래걸린다.  
Android Drawble Importer라는 플러그인을 사용해 해상도별 이미지를 만들고, 스마트폰 해상도에 따라 다른 사진을 보여줄 수 있다.   
>  플러그인 (plugin) - 안드로이드 스튜디오에서 기본적으로 제공하지 않는 기능을 제공
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

<!--    src로 이미지 경로 지정-->
<!--    이미지는 크기를 지정 : 어떤 디바이스에서 크게 보이거나 작게 보이진 않음-->
<!--    저해상도 핸드폰 : 고해상도 이미지를 그리는데 오래걸림-->
<!--    해상도 별로 준비된 이미지를 환경에 따라 자동으로 선택-->

   <ImageView
       android:layout_width="300dp"
       android:layout_height="300dp"
       android:src="@drawable/ic_launcher_foreground"/>

<!--    scaleType은 뷰 영역에 맞게 이미지를 확대, 축소하는 속성-->
   <ImageView
       android:layout_width="200dp"
       android:layout_height="200dp"
       android:background="#03A9F4"
       android:scaleType="centerCrop"
      android:src="@drawable/dog"/>

</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130102073-8439aa09-a781-478c-ae1b-f6e75c565963.png)

> scaleType 속성 - [블로그](https://blog.naver.com/beakdukhoo/222445968284)

# 과제

## 내가 작성한 코드
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="60dp"
        android:background="#000000"
        android:orientation="horizontal">

        <ImageView
            android:layout_width="60dp"
            android:layout_height="60dp"
            android:layout_centerVertical="true"
            android:layout_marginLeft="10dp"
            android:src="@drawable/you" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerVertical="true"
            android:layout_marginLeft="70dp"
            android:text="MyTube"
            android:textColor="#FFFFFF"
            android:textSize="25dp"
            android:textStyle="bold"/>
    </RelativeLayout>

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="#3A3838"
        android:fillViewport="true">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:orientation="vertical">

                <RelativeLayout
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="380dp"
                        android:layout_height="250dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="10dp"
                        android:background="#F8EDB5" />

                    <TextView
                        android:layout_width="40dp"
                        android:layout_height="22dp"
                        android:layout_marginLeft="347dp"
                        android:layout_marginTop="231dp"
                        android:background="#000000"
                        android:text="06:05"
                        android:textAlignment="center"
                        android:textColor="#ffffff" />


                </RelativeLayout>

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="70dp"
                    android:orientation="horizontal">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center"
                        android:layout_marginLeft="15dp"
                        android:src="@drawable/person" />

                    <LinearLayout
                        android:layout_width="320dp"
                        android:layout_height="match_parent"
                        android:orientation="vertical">

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:layout_marginTop="12dp"
                            android:paddingLeft="15dp"
                            android:text="안드로이드 1강"
                            android:textColor="#ffffff"
                            android:textSize="20dp" />

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:paddingLeft="15dp"
                            android:text="오늘의 강의 내용은..."
                            android:textColor="#ffffff"
                            android:textSize="13dp" />

                    </LinearLayout>
                </LinearLayout>
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:orientation="vertical">

                <RelativeLayout
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="380dp"
                        android:layout_height="250dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="10dp"
                        android:background="#EDDC82" />

                    <TextView
                        android:layout_width="40dp"
                        android:layout_height="22dp"
                        android:layout_marginLeft="347dp"
                        android:layout_marginTop="231dp"
                        android:background="#000000"
                        android:text="06:05"
                        android:textAlignment="center"
                        android:textColor="#ffffff" />


                </RelativeLayout>

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="70dp"
                    android:orientation="horizontal">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center"
                        android:layout_marginLeft="15dp"
                        android:src="@drawable/person" />

                    <LinearLayout
                        android:layout_width="320dp"
                        android:layout_height="match_parent"
                        android:orientation="vertical">

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:layout_marginTop="12dp"
                            android:paddingLeft="15dp"
                            android:text="안드로이드 1강"
                            android:textColor="#ffffff"
                            android:textSize="20dp" />

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:paddingLeft="15dp"
                            android:text="오늘의 강의 내용은..."
                            android:textColor="#ffffff"
                            android:textSize="13dp" />

                    </LinearLayout>
                </LinearLayout>
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:orientation="vertical">

                <RelativeLayout
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="380dp"
                        android:layout_height="250dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="10dp"
                        android:background="#F3DA5B" />

                    <TextView
                        android:layout_width="40dp"
                        android:layout_height="22dp"
                        android:layout_marginLeft="347dp"
                        android:layout_marginTop="231dp"
                        android:background="#000000"
                        android:text="06:05"
                        android:textAlignment="center"
                        android:textColor="#ffffff" />


                </RelativeLayout>

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="70dp"
                    android:orientation="horizontal">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center"
                        android:layout_marginLeft="15dp"
                        android:src="@drawable/person" />

                    <LinearLayout
                        android:layout_width="320dp"
                        android:layout_height="match_parent"
                        android:orientation="vertical">

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:layout_marginTop="12dp"
                            android:paddingLeft="15dp"
                            android:text="안드로이드 1강"
                            android:textColor="#ffffff"
                            android:textSize="20dp" />

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:paddingLeft="15dp"
                            android:text="오늘의 강의 내용은..."
                            android:textColor="#ffffff"
                            android:textSize="13dp" />

                    </LinearLayout>
                </LinearLayout>
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:orientation="vertical">

                <RelativeLayout
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="380dp"
                        android:layout_height="250dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="10dp"
                        android:background="#EDC705" />

                    <TextView
                        android:layout_width="40dp"
                        android:layout_height="22dp"
                        android:layout_marginLeft="347dp"
                        android:layout_marginTop="231dp"
                        android:background="#000000"
                        android:text="06:05"
                        android:textAlignment="center"
                        android:textColor="#ffffff" />


                </RelativeLayout>

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="70dp"
                    android:orientation="horizontal">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center"
                        android:layout_marginLeft="15dp"
                        android:src="@drawable/person" />

                    <LinearLayout
                        android:layout_width="320dp"
                        android:layout_height="match_parent"
                        android:orientation="vertical">

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:layout_marginTop="12dp"
                            android:paddingLeft="15dp"
                            android:text="안드로이드 1강"
                            android:textColor="#ffffff"
                            android:textSize="20dp" />

                        <TextView
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:paddingLeft="15dp"
                            android:text="오늘의 강의 내용은..."
                            android:textColor="#ffffff"
                            android:textSize="13dp" />

                    </LinearLayout>
                </LinearLayout>
            </LinearLayout>
        </LinearLayout>
    </ScrollView>

</LinearLayout>
```
![image](https://user-images.githubusercontent.com/86659995/130191039-213c7a78-d503-427a-899d-b4a2028e7c8c.png)

