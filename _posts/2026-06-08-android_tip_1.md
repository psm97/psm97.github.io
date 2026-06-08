---
title: "[Android(Java)] 예제1. 버튼을 누르면 버튼색과 배경색 변경하기"
excerpt: "안드로이드 스튜디오 Java 실습 예제 1"
categories:
  - 💻 Android (Java)
---

#### 개발환경
tools: Android Studio  
SDK: Android 9.0 (pie)  
개발언어: Java  

#### xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".MainActivity" >


    <TextView
        android:id="@+id/textView"
        android:layout_width="203dp"
        android:layout_height="29dp"
        android:layout_margin="20dp"
        android:hint="배경색"
        android:textAlignment="center"
        android:textSize="20sp" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical">

        <Button
            android:id="@+id/btn1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:hint="버튼1"
            android:backgroundTint="@color/purple"
            android:textSize="16sp" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="100" />

        <Button
            android:id="@+id/btn2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:hint="버튼2"
            android:backgroundTint="@color/teal"
            android:textSize="16sp" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="100" />


        <Button
            android:id="@+id/btn3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:hint="버튼3"
            android:backgroundTint="@color/yellow"
            android:textSize="16sp" />

    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1" />

</LinearLayout>
```

#### java
```java
package com.example.textchanger;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    final String TAG = "MainActivity";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView Text = (TextView) findViewById(R.id.textView);
        Button btn_one = (Button) findViewById(R.id.btn1);
        Button btn_two = (Button) findViewById(R.id.btn2);
        Button btn_three = (Button) findViewById(R.id.btn3);
        View background = findViewById(R.id.main);

        btn_one.setOnClickListener(new Button.OnClickListener() {
            public void onClick(View view) {
                Text.setText("purple");
                background.setBackgroundColor(getResources().getColor(R.color.purple));
                view.setBackgroundColor(view.getResources().getColor(R.color.purple));
            }
        });
        btn_two.setOnClickListener(new Button.OnClickListener() {
            @Override
            public void onClick(View view) {
                Text.setText("teal");
                background.setBackgroundColor(getResources().getColor(R.color.teal));
                view.setBackgroundColor(view.getResources().getColor(R.color.teal));
            }
        });
        btn_three.setOnClickListener(new Button.OnClickListener() {
            @Override
            public void onClick(View view) {
                Text.setText("yellow");
                background.setBackgroundColor(getResources().getColor(R.color.yellow));
                view.setBackgroundColor(view.getResources().getColor(R.color.yellow));
            }
        });
    }
}
```

#### 결과
![](/assets/images/exam/android_tip_1.gif){: width="300"}
