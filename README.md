# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. Start the project: Create a new Android project in Android Studio.
2. Design the UI: In activity_main.xml, add an EditText (to accept the URL input) and a Button (to trigger the navigation).
3. Initialize components: In MainActivity.java, map the EditText and Button variables to their respective XML IDs using findViewById().
4. Set click listener: Attach an OnClickListener to the button to listen for user click events.
5. Get input: Inside the onClick method, extract the text entered in the EditText and convert it to a string.
6. Create implicit intent: Instantiate an Intent with the action Intent.ACTION_VIEW and pass the parsed URL string using Uri.parse().
7. Start activity: Call startActivity(intent) to trigger the OS to open the webpage in an available web browser.
8. Execution: Run and test the application.

## PROGRAM:
```
Program to print the text “Implicitintent”.
Developed by: KOWSHIK RAM S
Registeration Number : 212225230413
```
## activity_main.xml :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="236dp"
        android:layout_height="53dp"
        android:fontFamily="sans-serif-black"
        android:text="Implicit Intent"
        android:textSize="34sp"
        app:layout_constraintBottom_toTopOf="@+id/editTextText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.509" />

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="218dp"
        android:layout_height="64dp"
        android:layout_marginBottom="184dp"
        android:ems="10"
        android:inputType="text"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="163dp"
        android:layout_height="58dp"
        android:layout_marginBottom="156dp"
        android:text="CLICK"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java :
```
package com.example.implicitintent;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    EditText editText;
    Button button;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        editText = findViewById(R.id.editTextText);
        button = findViewById(R.id.button);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String url = editText.getText().toString().trim();
                if (!url.startsWith("http://") && !url.startsWith("https://")) {
                    url = "https://" + url;
                }
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}
```

## OUTPUT

<img width="1632" height="872" alt="Screenshot 2026-11-04 100248" src="https://github.com/user-attachments/assets/020e1758-b3cd-4b6d-82d6-2970f08a24a1" />




<img width="1717" height="917" alt="image" src="https://github.com/user-attachments/assets/e2f22828-95de-4e4e-bb0b-40467d89491b" />





## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.
