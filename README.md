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
Developed by:
Registeration Number :
*/
```
### AndroidManifest.xml
```xml
    <uses-permission android:name="android.permission.BODY_SENSORS"/>
```
### MainActivity.java
```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <uses-permission android:name="android.permission.BODY_SENSORS"/>
    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ProximitySensorApp">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
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
