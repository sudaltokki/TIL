# 과제 - 덧셈 계산기 

## Activity 파일

```kotlin
package com.example.app1

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.TextView

class Calculator : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_calculator)

        val zero: TextView = findViewById(R.id.zero)
        val one: TextView = findViewById(R.id.one)
        val two: TextView = findViewById(R.id.two)
        val three: TextView = findViewById(R.id.three)
        val four: TextView = findViewById(R.id.four)
        val five: TextView = findViewById(R.id.five)
        val six: TextView = findViewById(R.id.six)
        val seven: TextView = findViewById(R.id.seven)
        val eight: TextView = findViewById(R.id.eight)
        val nine: TextView = findViewById(R.id.nine)
        val plus: TextView = findViewById(R.id.plus)
        val reset: TextView = findViewById(R.id.reset)
        val number: TextView = findViewById(R.id.number)

        zero.setOnClickListener{
            if (new != "0") new = new + "0"
            number.setText(new)
        }
        one.setOnClickListener{
            if (new != "0") new = new + "1"
            else new = "1"
            number.setText(new)
        }
        two.setOnClickListener{
            if (new != "0") new = new + "2"
            else new = "2"
            number.setText(new)
        }
        three.setOnClickListener{
            if (new != "0") new = new + "3"
            else new = "3"
            number.setText(new)
        }
        four.setOnClickListener{
            if (new != "0") new = new + "4"
            else new = "4"
            number.setText(new)
        }
        five.setOnClickListener{
            if (new != "0") new = new + "5"
            else new = "5"
            number.setText(new)
        }
        six.setOnClickListener{
            if (new != "0") new = new + "6"
            else new = "6"
            number.setText(new)
        }
        seven.setOnClickListener{
            if (new != "0") new = new + "7"
            else new = "7"
            number.setText(new)
        }
        eight.setOnClickListener{
            if (new != "0") new = new + "8"
            else new = "8"
            number.setText(new)
        }
        nine.setOnClickListener{
            if (new != "0") new = new + "9"
            else new = "9"
            number.setText(new)
        }

        plus.setOnClickListener {
            old = (old.toInt() + new.toInt()).toString()
            new = "0"
            number.setText(old)
        }
        reset.setOnClickListener{
            new = ""
            old = "0"
            number.setText("")
        }



    }
}

var new = ""
var old = "0"
```

## Layout 파일

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Calculator"
    android:orientation="vertical">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#ffffff">

        <TextView
            android:id="@+id/number"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:gravity="center_vertical|right"
            android:paddingTop="9dp"
            android:paddingBottom="9dp"
            android:paddingRight="15dp"
            android:textColor="#000000"
            android:textSize="50dp"
            android:text=""/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <LinearLayout
            android:layout_weight="1"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:orientation="horizontal">

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/one"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="1"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/two"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="2"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/three"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="3"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#80C7E8">

                <TextView
                    android:id="@+id/reset"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="CA"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>
        </LinearLayout>

        <LinearLayout
            android:layout_weight="1"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:orientation="horizontal">

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/four"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="4"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/five"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="5"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#ECE4A3">

                <TextView
                    android:id="@+id/six"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="6"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:background="#80C7E8">

                <TextView
                    android:id="@+id/plus"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="+"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>
        </LinearLayout>

        <LinearLayout
            android:layout_weight="1"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:background="#ECE4A3"
            android:orientation="horizontal">

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent">

                <TextView
                    android:id="@+id/seven"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="7"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent">

                <TextView
                    android:id="@+id/eight"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="8"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent">

                <TextView
                    android:id="@+id/nine"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="9"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>

            <LinearLayout
                android:layout_weight="1"
                android:layout_width="0dp"
                android:layout_height="match_parent">

                <TextView
                    android:id="@+id/zero"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:gravity="center"
                    android:text="0"
                    android:textColor="#000000"
                    android:textSize="50dp"/>
            </LinearLayout>
        </LinearLayout>



    </LinearLayout>


</LinearLayout>
```
<img src="https://user-images.githubusercontent.com/86659995/130567310-f56a272a-80cd-4e32-b2a9-a01587393561.png" width="200" height="400"/>

= 대신 +를 한 번 더 눌러야 계산이 작동한다.  
강의 코드와 달리 앞에 0이 붙는것을 없애고 싶어서 추가적으로 코드를 작성했다.  
처음에 나는 뒤에 숫자를 누를때 앞에 누른 숫자에 10을 곱해서 더하는 식으로 작성했었는데 강의 풀이가 더 간결한 것 같아 수정했다.
