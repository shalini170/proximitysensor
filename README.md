# Ex.No:5 Develop a simple application for proximity sensor using Sensor Manager in android studio.


## AIM:

To develop a sensor application for proximity sensor using sensor manager in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Giraffe)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as proximitysensor and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display process of proximitysensor in android mobile devices.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the process of proximitysensor in android mobile devices”.
Developed by:shalini venkatesulu
Registeration Number :212223220104
*/
```
### AndroidManifest.xml
```xml
    <uses-permission android:name="android.permission.BODY_SENSORS"/>
```
### MainActivity.java
```java
package com.example.proximitysensorapp;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity implements SensorEventListener {

    private SensorManager sensorManager;
    private Sensor proximitySensor;
    private TextView tvStatus, tvDistance, tvMaxRange, tvAvailable;
    private boolean isSensorAvailable = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize TextViews
        tvStatus = findViewById(R.id.tvStatus);
        tvDistance = findViewById(R.id.tvDistance);
        tvMaxRange = findViewById(R.id.tvMaxRange);
        tvAvailable = findViewById(R.id.tvAvailable);

        // Get SensorManager
        sensorManager = (SensorManager) getSystemService(Context.SENSOR_SERVICE);

        // Get Proximity Sensor
        if (sensorManager != null) {
            proximitySensor = sensorManager.getDefaultSensor(Sensor.TYPE_PROXIMITY);

            if (proximitySensor != null) {
                isSensorAvailable = true;
                tvAvailable.setText("Sensor: Available ✓");
                tvMaxRange.setText("Max Range: " + proximitySensor.getMaximumRange() + " cm");
            } else {
                tvAvailable.setText("Sensor: Not Available ✗");
                tvStatus.setText("NO SENSOR");
                tvMaxRange.setText("Max Range: N/A");
            }
        }
    }

    @Override
    protected void onResume() {
        super.onResume();
        // Register sensor listener
        if (isSensorAvailable) {
            sensorManager.registerListener(this, proximitySensor, SensorManager.SENSOR_DELAY_NORMAL);
        }
    }

    @Override
    protected void onPause() {
        super.onPause();
        // Unregister sensor listener to save battery
        if (isSensorAvailable) {
            sensorManager.unregisterListener(this);
        }
    }

    @Override
    public void onSensorChanged(SensorEvent event) {
        if (event.sensor.getType() == Sensor.TYPE_PROXIMITY) {
            float distance = event.values[0];

            // Update distance display
            tvDistance.setText("Distance: " + distance + " cm");

            // Check proximity status
            if (distance < proximitySensor.getMaximumRange()) {
                // Object is NEAR
                tvStatus.setText("NEAR");
                tvStatus.setTextColor(getResources().getColor(android.R.color.holo_red_dark));
                // Change background color (optional - would need programmatic background change)
            } else {
                // Object is FAR
                tvStatus.setText("FAR");
                tvStatus.setTextColor(getResources().getColor(android.R.color.holo_green_dark));
            }
        }
    }

    @Override
    public void onAccuracyChanged(Sensor sensor, int accuracy) {
        // Handle accuracy changes if needed
    }
}
```
### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    android:background="#121212">

    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Proximity Sensor"
        android:textSize="28sp"
        android:textColor="#4CAF50"
        android:textStyle="bold"
        android:layout_marginBottom="40dp"/>

    <LinearLayout
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:gravity="center"
        android:background="@drawable/circle_background"
        android:layout_marginBottom="30dp">

        <TextView
            android:id="@+id/tvStatus"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="FAR"
            android:textSize="24sp"
            android:textColor="#FFFFFF"
            android:textStyle="bold"/>
    </LinearLayout>

    <TextView
        android:id="@+id/tvDistance"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Distance: 0.0 cm"
        android:textSize="18sp"
        android:textColor="#E0E0E0"
        android:layout_marginBottom="20dp"/>

    <TextView
        android:id="@+id/tvMaxRange"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Max Range: "
        android:textSize="16sp"
        android:textColor="#BBBBBB"/>

    <TextView
        android:id="@+id/tvAvailable"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Sensor: Checking..."
        android:textSize="14sp"
        android:textColor="#888888"
        android:layout_marginTop="30dp"/>

</LinearLayout>
```
### circle Background.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="oval">

    <solid android:color="#2196F3"/>
    <size
        android:width="200dp"
        android:height="200dp"/>

</shape>
```

## OUTPUT
<img width="2876" height="1792" alt="image" src="https://github.com/user-attachments/assets/37e8ed7e-5367-4978-be7f-5a198f597eae" />

<img width="2811" height="1721" alt="image" src="https://github.com/user-attachments/assets/4465611a-fe8d-43fd-9d30-0b7056358500" />
<img width="2798" height="1726" alt="image" src="https://github.com/user-attachments/assets/1770ff87-24d5-4d0c-a9db-9710e2d1cc9d" />







## RESULT
Thus a Simple Android Application to display the details of proximity sensor using sensor manager in Android Studio is developed and executed successfully.
