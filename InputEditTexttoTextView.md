# Introduction #
ตัวอย่างการรับค่าจาก Input จาก EditText แล้วนำมาใส่ใน TextView

[เอามาจากตัวอย่าง การรับ Input จาก EditText แล้วพ่นไปเป็น TextView](http://www.androidthai.in.th/conternt-android/122-input-edittext-to-textview.html)

![https://lh6.googleusercontent.com/-KucGiiCh87M/UKIoKY_q5jI/AAAAAAAAFMY/Qq5SzVajJAA/s720/2012-11-13%252017.48.46.jpg](https://lh6.googleusercontent.com/-KucGiiCh87M/UKIoKY_q5jI/AAAAAAAAFMY/Qq5SzVajJAA/s720/2012-11-13%252017.48.46.jpg)

ใส่ชื่อ User เข้าไป

![https://lh3.googleusercontent.com/-bxNcYNVBrw8/UKIoTMlEZuI/AAAAAAAAFMg/ihc7DKMqy0E/s720/2012-11-13%252017.48.582.jpg](https://lh3.googleusercontent.com/-bxNcYNVBrw8/UKIoTMlEZuI/AAAAAAAAFMg/ihc7DKMqy0E/s720/2012-11-13%252017.48.582.jpg)

แสดงชื่อ User ออกมา

![https://lh6.googleusercontent.com/-UAJBOWmK9og/UKIoTM4DzKI/AAAAAAAAFMk/qeZOzWwNb-k/s720/2012-11-13%252017.48.58.jpg](https://lh6.googleusercontent.com/-UAJBOWmK9og/UKIoTM4DzKI/AAAAAAAAFMk/qeZOzWwNb-k/s720/2012-11-13%252017.48.58.jpg)

# Details #
  * MainActivity.java
```java

package com.app.hellouser;

import android.app.Activity;
import android.os.Bundle;
import android.view.Menu;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.view.View.OnClickListener;

public class MainActivity extends Activity {

private EditText edtInput;
private TextView txtInput;
private Button btnHitMe;

@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

edtInput = (EditText)findViewById(R.id.edtInput);
txtInput = (TextView)findViewById(R.id.txtInput);
btnHitMe = (Button)findViewById(R.id.btnHitMe);

btnHitMe.setOnClickListener(new OnClickListener(){

@Override
public void onClick(View v) {
// TODO Auto-generated method stub
txtInput.setText(edtInput.getText().toString());
}
});
}

@Override
public boolean onCreateOptionsMenu(Menu menu) {
getMenuInflater().inflate(R.menu.activity_main, menu);
return true;
}
}

```

  * activity\_main.xml
```xml

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:layout_alignParentLeft="true"
android:layout_alignParentRight="true"
android:layout_alignParentTop="true"
android:orientation="vertical" >

<TextView
android:id="@+id/textView1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/fill_name"
android:textSize="20dp"
android:textStyle="bold" />

<EditText
android:id="@+id/edtInput"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:ems="10"
android:hint="@string/please"
android:inputType="text" >

<requestFocus />


Unknown end tag for &lt;/EditText&gt;





<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content" >


<TextView
android:id="@+id/textView2"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/welcome"
android:textSize="20dp" />

<TextView
android:id="@+id/txtInput"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/name"
android:textSize="20dp" />



Unknown end tag for &lt;/LinearLayout&gt;



<Button
android:id="@+id/btnHitMe"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_gravity="center_horizontal"
android:text="@string/hit_me"
android:textSize="20dp" />



Unknown end tag for &lt;/LinearLayout&gt;


```

  * strings.xml
```xml

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:layout_alignParentLeft="true"
android:layout_alignParentRight="true"
android:layout_alignParentTop="true"
android:orientation="vertical" >

<TextView
android:id="@+id/textView1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/fill_name"
android:textSize="20dp"
android:textStyle="bold" />

<EditText
android:id="@+id/edtInput"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:ems="10"
android:hint="@string/please"
android:inputType="text" >

<requestFocus />


Unknown end tag for &lt;/EditText&gt;





<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content" >


<TextView
android:id="@+id/textView2"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/welcome"
android:textSize="20dp" />

<TextView
android:id="@+id/txtInput"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/name"
android:textSize="20dp" />



Unknown end tag for &lt;/LinearLayout&gt;



<Button
android:id="@+id/btnHitMe"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_gravity="center_horizontal"
android:text="@string/hit_me"
android:textSize="20dp" />



Unknown end tag for &lt;/LinearLayout&gt;


```