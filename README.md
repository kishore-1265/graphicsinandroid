
# Ex.No: 07 Design an application that draws basic graphical primitives on the screen.


## AIM:

To create and design an android application that draws basic graphical primitives on the screen using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “graphical″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Draw basic object details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application that draws basic graphical primitives on the screen.
Developed by: Kishore R
Registeration Number : 212225040192
*/
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="?android:attr/colorBackground">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Graphical Primitives"
        android:textSize="24sp"
        android:textStyle="bold"
        android:textColor="?attr/colorOnPrimary"
        android:gravity="center"
        android:padding="20dp"
        android:layout_marginTop="30dp"
        android:background="?attr/colorPrimary"/>

    <view
        class="com.example.graphicprimitives.MainActivity$DrawingView"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"/>

</LinearLayout>

```
## mainactivity.java
```
package com.example.graphicprimitives;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Paint;
import android.os.Bundle;
import android.util.AttributeSet;
import android.view.View;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.content.ContextCompat;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public static class DrawingView extends View {

        private Paint paint;

        public DrawingView(Context context) {
            super(context);
            init();
        }

        public DrawingView(Context context, @Nullable AttributeSet attrs) {
            super(context, attrs);
            init();
        }

        public DrawingView(Context context, @Nullable AttributeSet attrs, int defStyleAttr) {
            super(context, attrs, defStyleAttr);
            init();
        }

        private void init() {
            paint = new Paint(Paint.ANTI_ALIAS_FLAG);
            paint.setTextSize(44f);
        }

        @Override
        protected void onDraw(@NonNull Canvas canvas) {
            super.onDraw(canvas);

            float width = getWidth();
            float height = getHeight();
            float centerX = width / 2;
            float size = width * 0.18f;

            int textColor = ContextCompat.getColor(getContext(), R.color.on_background);
            int circleColor = ContextCompat.getColor(getContext(), R.color.shape_circle);
            int rectColor = ContextCompat.getColor(getContext(), R.color.shape_rectangle);
            int lineColor = ContextCompat.getColor(getContext(), R.color.shape_line);
            int squareColor = ContextCompat.getColor(getContext(), R.color.shape_square);

            // 1. Circle
            paint.setStyle(Paint.Style.FILL);
            paint.setColor(circleColor);
            canvas.drawCircle(centerX, height * 0.12f, size, paint);

            paint.setColor(textColor);
            paint.setTextAlign(Paint.Align.CENTER);
            paint.setStyle(Paint.Style.FILL);
            canvas.drawText("Circle", centerX, height * 0.24f, paint);

            // 2. Rectangle
            paint.setColor(rectColor);
            canvas.drawRect(centerX - size, height * 0.30f,
                    centerX + size, height * 0.40f, paint);

            paint.setColor(textColor);
            canvas.drawText("Rectangle", centerX, height * 0.44f, paint);

            // 3. Line
            paint.setColor(lineColor);
            paint.setStyle(Paint.Style.STROKE);
            paint.setStrokeWidth(16f);
            canvas.drawLine(centerX - size, height * 0.52f,
                    centerX + size, height * 0.52f, paint);

            paint.setStyle(Paint.Style.FILL);
            paint.setColor(textColor);
            canvas.drawText("Line", centerX, height * 0.58f, paint);

            // 4. Square
            paint.setColor(squareColor);
            canvas.drawRect(centerX - size, height * 0.64f,
                    centerX + size, height * 0.64f + (size * 2), paint);

            paint.setColor(textColor);
            canvas.drawText("Square", centerX, height * 0.64f + (size * 2) + 50f, paint);
        }
    }
}

```

## OUTPUT

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/6b286953-fe5a-48b2-bae2-458928fcff85" />

<img width="1912" height="1078" alt="image" src="https://github.com/user-attachments/assets/5f0b1321-e604-4bb5-9683-dc13002b7503" />


## RESULT
Thus a Simple Android Application to create and design an android application that draws basic graphical primitives on the screen using Android Studio is developed and executed successfully.
