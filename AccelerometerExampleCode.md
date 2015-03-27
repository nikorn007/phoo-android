# Introduction #
![http://1.bp.blogspot.com/-sHap1-PUUjs/UH5J3ziW_rI/AAAAAAAAEhQ/F9n90K2hOf4/s1600/Screenshot_2012-10-16-23-07-24.png](http://1.bp.blogspot.com/-sHap1-PUUjs/UH5J3ziW_rI/AAAAAAAAEhQ/F9n90K2hOf4/s1600/Screenshot_2012-10-16-23-07-24.png)


ตัวอย่างนี้จะแสดงค่าของเซนเซอร์วัดความเร่ง (Accelerometer) ทั้ง 3 แกน คือ X, Y และ Z อย่างง่ายๆ โดยในตัวอย่างนี้ ค่าของทั้ง 3 แกนจะไม่นิ่งเป็น 0 เมื่อว่างอยู่นิ่งๆ ซึ่งตัวอย่างนี้จะไม่สามารถทดสอบบน Emulator ได้นะครับ

![http://2.bp.blogspot.com/-ADXY9QDhz6Y/UH5Kme_XtUI/AAAAAAAAEhY/IBZT21_h51o/s1600/axis_device.png](http://2.bp.blogspot.com/-ADXY9QDhz6Y/UH5Kme_XtUI/AAAAAAAAEhY/IBZT21_h51o/s1600/axis_device.png)

# Details #

  * AccelerometerTestActivity.java

```java

package com.example.accelerometertest;

import android.app.Activity;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.view.Menu;
import android.widget.TextView;

public class AccelerometerTestActivity extends Activity implements
SensorEventListener {

private SensorManager sensorManager;

TextView xCoor; // declare X axis object
TextView yCoor; // declare Y axis object
TextView zCoor; // declare Z axis object

@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_accelerometer_test);

xCoor = (TextView) findViewById(R.id.xcoor); // create X axis object
yCoor = (TextView) findViewById(R.id.ycoor); // create Y axis object
zCoor = (TextView) findViewById(R.id.zcoor); // create Z axis object

sensorManager = (SensorManager) getSystemService(SENSOR_SERVICE);
// add listener. The listener will be HelloAndroid (this) class
sensorManager.registerListener(this,
sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER),
SensorManager.SENSOR_DELAY_NORMAL);

/*
* More sensor speeds (taken from api docs) SENSOR_DELAY_FASTEST get
* sensor data as fast as possible SENSOR_DELAY_GAME rate suitable for
* games SENSOR_DELAY_NORMAL rate (default) suitable for screen
* orientation changes
*/

}

public void onAccuracyChanged(Sensor sensor, int accuracy) {

}

public void onSensorChanged(SensorEvent event) {

// check sensor type
if (event.sensor.getType() == Sensor.TYPE_ACCELEROMETER) {

// assign directions
float x = event.values[0];
float y = event.values[1];
float z = event.values[2];

xCoor.setText("X: " + x);
yCoor.setText("Y: " + y);
zCoor.setText("Z: " + z);
}
}

@Override
public boolean onCreateOptionsMenu(Menu menu) {
getMenuInflater().inflate(R.menu.activity_accelerometer_test, menu);
return true;
}
}

```

  * activity\_accelerometer\_test.xml
```xml

<?xml version="1.0" encoding="utf-8"?>
<TableLayout
xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="fill_parent"
android:layout_height="fill_parent">

<TableRow>

<TextView
android:id="@+id/xcoor"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/xcoor" />



Unknown end tag for &lt;/TableRow&gt;



<TableRow>

<TextView
android:id="@+id/ycoor"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/ycoor" />



Unknown end tag for &lt;/TableRow&gt;



<TableRow>

<TextView
android:id="@+id/zcoor"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="@string/zcoor" />



Unknown end tag for &lt;/TableRow&gt;





Unknown end tag for &lt;/TableLayout&gt;


```

  * strings.xml
```xml

<resources>
<string name="app_name">AccelerometerTest

Unknown end tag for &lt;/string&gt;


<string name="hello_world">Hello world!

Unknown end tag for &lt;/string&gt;


<string name="menu_settings">Settings

Unknown end tag for &lt;/string&gt;


<string name="title_activity_accelerometer_test">AccelerometerTestActivity

Unknown end tag for &lt;/string&gt;


<string name="xcoor">X-Coordinator :

Unknown end tag for &lt;/string&gt;


<string name="ycoor">Y-Coordinator :

Unknown end tag for &lt;/string&gt;


<string name="zcoor">Z-Coordinator :

Unknown end tag for &lt;/string&gt;




Unknown end tag for &lt;/resources&gt;


```

  * AndroidManiFest.xml
```xml

<manifest xmlns:android="http://schemas.android.com/apk/res/android"
package="com.example.accelerometertest"
android:versionCode="1"
android:versionName="1.0" >
<uses-sdk
android:minSdkVersion="8"
android:targetSdkVersion="15" />
<uses-permission android:name="android.permission.INTERNET" />
<application
android:icon="@drawable/ic_launcher"
android:label="@string/app_name"
android:theme="@style/AppTheme"
android:debuggable="true" >
<activity
android:name=".AccelerometerTestActivity"
android:label="@string/title_activity_accelerometer_test" >
<intent-filter>
<action android:name="android.intent.action.MAIN" />
<category android:name="android.intent.category.LAUNCHER" />


Unknown end tag for &lt;/intent-filter&gt;




Unknown end tag for &lt;/activity&gt;




Unknown end tag for &lt;/application&gt;




Unknown end tag for &lt;/manifest&gt;


```