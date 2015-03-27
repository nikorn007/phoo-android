# Introduction #

![https://lh5.googleusercontent.com/-yJwragqqCxY/UKpK_v2AyUI/AAAAAAAAFQg/IVkVwnkvcLQ/s830/2012-11-19%252021.20.48.jpg](https://lh5.googleusercontent.com/-yJwragqqCxY/UKpK_v2AyUI/AAAAAAAAFQg/IVkVwnkvcLQ/s830/2012-11-19%252021.20.48.jpg)

ในตัวอย่างจะมี Activity อยู่ 3 แบบ 3 Layout แต่ละอันแยกอิสระต่อกัน

Credited : http://www.thaicreate.com/mobile/android-intent-activity.html


# Details #

![https://lh5.googleusercontent.com/-hxjoIiv5C94/UKpIzeLVybI/AAAAAAAAFQI/Kfn3ETEY6YE/s512/11-19-2012%25209-38-58%2520PM.jpg](https://lh5.googleusercontent.com/-hxjoIiv5C94/UKpIzeLVybI/AAAAAAAAFQI/Kfn3ETEY6YE/s512/11-19-2012%25209-38-58%2520PM.jpg)

**AndroidManifest.xml**```xml

<manifest xmlns:android="http://schemas.android.com/apk/res/android"
package="com.app.androidintent"
android:versionCode="1"
android:versionName="1.0" >
<uses-sdk
android:minSdkVersion="8"
android:targetSdkVersion="15" />
<application
android:icon="@drawable/ic_launcher"
android:label="@string/app_name"
android:theme="@style/AppTheme" >
<activity
android:name=".MainActivity"
android:label="@string/title_activity_main" >
<intent-filter>
<action android:name="android.intent.action.MAIN" />
<category android:name="android.intent.category.LAUNCHER" />


Unknown end tag for &lt;/intent-filter&gt;




Unknown end tag for &lt;/activity&gt;


<activity
android:name="Activity1"
android:theme="@style/AppTheme"
android:screenOrientation="portrait"
android:label ="@string/title_activity_main" />
<activity
android:name="Activity2"
android:theme="@style/AppTheme"
android:screenOrientation="portrait"
android:label="@string/title_activity_main" />


Unknown end tag for &lt;/application&gt;




Unknown end tag for &lt;/manifest&gt;


```

  * MainActivity.java
```java

package com.app.androidintent;

import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.Menu;
import android.view.View;
import android.widget.Button;

public class MainActivity extends Activity {

@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

// Button1
final Button btn1 = (Button) findViewById(R.id.button1);
// Perform action on click
btn1.setOnClickListener(new View.OnClickListener() {
public void onClick(View v) {

// Open Form 2
Intent newActivity = new Intent(MainActivity.this,Activity1.class);
startActivity(newActivity);

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

  * Activity1.java
```java

package com.app.androidintent;

import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class Activity1 extends Activity {

@Override
public void onCreate(Bundle savedInstanceState){
super.onCreate(savedInstanceState);
setContentView(R.layout.activity1);

// Button1
final Button btn1 = (Button) findViewById(R.id.button1);
// Perform action on click
btn1.setOnClickListener(new View.OnClickListener() {
public void onClick(View v) {

// Open Form 3
Intent newActivity = new Intent(Activity1.this,Activity2.class);
startActivity(newActivity);

}
});

}

}

```

  * Activity2.java
```java

package com.app.androidintent;

import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class Activity2 extends Activity {

@Override
public void onCreate(Bundle savedInstanceState){
super.onCreate(savedInstanceState);
setContentView(R.layout.activity2);

// Button1
final Button btn1 = (Button) findViewById(R.id.button1);
// Perform action on click
btn1.setOnClickListener(new View.OnClickListener() {
public void onClick(View v) {

// Open Form 3
Intent newActivity = new Intent(Activity2.this, MainActivity.class);
startActivity(newActivity);

}
});

}

}

```

  * activity\_main.xml
```xml

<RelativeLayout   xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent" >
<TextView
android:id="@+id/textView1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_alignParentTop="true"
android:layout_centerHorizontal="true"
android:layout_marginTop="50dp"
android:text="@string/current_main_act"
android:textAppearance="?android:attr/textAppearanceLarge" />
<Button
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_below="@+id/textView1"
android:layout_centerHorizontal="true"
android:layout_marginTop="62dp"
android:text="@string/show_act1" />


Unknown end tag for &lt;/RelativeLayout&gt;


```

  * activity1.xml
```xml

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical" >
<TextView
android:id="@+id/textView1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_alignParentTop="true"
android:layout_centerHorizontal="true"
android:layout_marginTop="50dp"
android:text="@string/current_act1"
android:textAppearance="?android:attr/textAppearanceLarge" />
<Button
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_below="@+id/textView1"
android:layout_centerHorizontal="true"
android:layout_marginTop="62dp"
android:text="@string/show_act2" />


Unknown end tag for &lt;/RelativeLayout&gt;



```

  * activity2.xml
```xml

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical" >
<TextView
android:id="@+id/textView1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_alignParentTop="true"
android:layout_centerHorizontal="true"
android:layout_marginTop="50dp"
android:text="@string/current_act2"
android:textAppearance="?android:attr/textAppearanceLarge" />
<Button
android:id="@+id/button1"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:layout_below="@+id/textView1"
android:layout_centerHorizontal="true"
android:layout_marginTop="62dp"
android:text="@string/show_main_act" />


Unknown end tag for &lt;/RelativeLayout&gt;


```

  * strings.xml
```xml

<resources>

<string name="app_name">AndroidIntent

Unknown end tag for &lt;/string&gt;



<string name="hello_world">Hello world!

Unknown end tag for &lt;/string&gt;



<string name="menu_settings">Settings

Unknown end tag for &lt;/string&gt;



<string name="title_activity_main">Android Intent

Unknown end tag for &lt;/string&gt;



<string name="current_act1">Current Show Activity 1

Unknown end tag for &lt;/string&gt;



<string name="current_act2">Current Show Activity2

Unknown end tag for &lt;/string&gt;



<string name="current_main_act">Current Show Main Activity

Unknown end tag for &lt;/string&gt;



<string name="show_act1">Show Activity1

Unknown end tag for &lt;/string&gt;



<string name="show_act2">Show Activity2

Unknown end tag for &lt;/string&gt;



<string name="show_main_act">Show Main Activity

Unknown end tag for &lt;/string&gt;





Unknown end tag for &lt;/resources&gt;


```

