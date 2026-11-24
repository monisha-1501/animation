## EX:NO:06 IMPLEMENTATION OF ANIMATION IN ANDROID APPLICATIONS.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as "androidanimation" and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create a anim folder under res and create the xml files for the animation operators.

Step 7: Add animation operations in MainActivity file.

Step 8: Save and run the application.


## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Monisha D
Registeration Number : 212225240090
*/
```
### MainActivity.java
```
package com.example.animation;

import android.os.Bundle;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

import com.example.animation.R;

public class MainActivity extends AppCompatActivity {

    ImageView img;

    Button btnBlink;
    Button btnRotate;
    Button btnFade;
    Button btnMove;
    Button btnSlide;
    Button btnZoom;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        img = findViewById(R.id.img);

        btnBlink = findViewById(R.id.btnBlink);
        btnRotate = findViewById(R.id.btnRotate);
        btnFade = findViewById(R.id.btnFade);
        btnMove = findViewById(R.id.btnMove);
        btnSlide = findViewById(R.id.btnSlide);
        btnZoom = findViewById(R.id.btnZoom);

        btnBlink.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.blink);
            img.startAnimation(animation);
        });

        btnRotate.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.rotate);
            img.startAnimation(animation);
        });

        btnFade.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.fade);
            img.startAnimation(animation);
        });

        btnMove.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.move);
            img.startAnimation(animation);
        });

        btnSlide.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.slide);
            img.startAnimation(animation);
        });

        btnZoom.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(this, R.anim.zoom);
            img.startAnimation(animation);
        });
    }
}
```

### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>

<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center"
        android:padding="20dp">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginBottom="20dp"
            android:text="FLOWER ANIMATION"
            android:textSize="24sp"
            android:textStyle="bold" />

        <ImageView
            android:id="@+id/img"
            android:layout_width="180dp"
            android:layout_height="180dp"
            android:layout_marginBottom="25dp"
            android:contentDescription="Flower Image"
            android:scaleType="fitCenter"
            android:src="@drawable/flower" />

        <Button
            android:id="@+id/btnBlink"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="BLINK" />

        <Button
            android:id="@+id/btnRotate"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="ROTATE" />

        <Button
            android:id="@+id/btnFade"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="FADE" />

        <Button
            android:id="@+id/btnMove"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="MOVE" />

        <Button
            android:id="@+id/btnSlide"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="SLIDE" />

        <Button
            android:id="@+id/btnZoom"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="ZOOM" />

    </LinearLayout>

</ScrollView>
```

### blink.xml
```
<?xml version="1.0" encoding="utf-8"?>

<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="500"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:repeatCount="3"
    android:repeatMode="reverse" />
```

### rotate.xml
```
<?xml version="1.0" encoding="utf-8"?>

<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="1000"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:repeatCount="2"
    android:repeatMode="restart" />
```

### fade.xml
```
<?xml version="1.0" encoding="utf-8"?>

<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="1000"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:repeatCount="1"
    android:repeatMode="reverse" />
```

### move.xml
```
<?xml version="1.0" encoding="utf-8"?>

<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="1000"
    android:fromXDelta="0"
    android:toXDelta="300"
    android:fromYDelta="0"
    android:toYDelta="300"
    android:repeatCount="1"
    android:repeatMode="reverse" />
```

### slide.xml
```
<?xml version="1.0" encoding="utf-8"?>

<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="1000"
    android:fromXDelta="-100%"
    android:toXDelta="0%"
    android:repeatCount="0" />
```

### zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>

<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="1000"
    android:fromXScale="1.0"
    android:toXScale="2.0"
    android:fromYScale="1.0"
    android:toYScale="2.0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:repeatCount="1"
    android:repeatMode="reverse" />
```

### string.xml
```
<resources>
    <string name="app_name">GFG App</string>
    <string name="blink">BLINK</string>
    <string name="clockwise">ROTATE</string>
    <string name="fade">FADE</string>
    <string name="move">MOVE</string>
    <string name="slide">SLIDE</string>
    <string name="zoom">ZOOM</string>
    <string name="stop_animation">STOP ANIMATION</string>
    <string name="course_rating">Course Rating</string>
    <string name="course_name">Course Name</string>
</resources>
```

## OUTPUT


<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/84e5c364-b505-4f43-9bbe-fb5a86e04406" />

<img width="1920" height="1200" alt="Screenshot (263)" src="https://github.com/user-attachments/assets/a269f8fb-4d2a-449c-bf1f-1b35528d3d29" />

<img width="1920" height="1200" alt="Screenshot (262)" src="https://github.com/user-attachments/assets/ec745d32-5c05-465c-b094-a355e72815f4" />

<img width="1920" height="1200" alt="Screenshot (263)" src="https://github.com/user-attachments/assets/cfda0b6b-b14f-48cf-ab5d-dbcf68f27066" />

<img width="1920" height="1200" alt="Screenshot (264)" src="https://github.com/user-attachments/assets/4d0c8fda-003f-4603-b83b-baddc75a6bd7" />

<img width="1920" height="1200" alt="Screenshot (265)" src="https://github.com/user-attachments/assets/6b61e216-9754-45bc-87cd-4dd6e56d3105" />

<img width="1920" height="1200" alt="Screenshot (266)" src="https://github.com/user-attachments/assets/aa3c43fd-0a67-4942-8a0e-d21ca04e7ff1" />

## RESULT

The Android Image Animation app was successfully developed to perform blink, rotate, fade, move, slide, and zoom animations on a custom image.
