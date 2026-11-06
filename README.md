# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:




## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: SAIDESHIYA K
Registeration Number : 21224220084
*/

```
## MainActivity.java:
```
package com.example.explicit;

import android.os.Bundle;
import android.content.Intent;
import android.widget.EditText;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText number;
    Button btnFactorial;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        number = findViewById(R.id.number);
        btnFactorial = findViewById(R.id.btnFactorial);

        btnFactorial.setOnClickListener(v -> {

            String input = number.getText().toString();

            if (input.isEmpty()) {
                Toast.makeText(this, "Enter a number",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            int n = Integer.parseInt(input);

            if (n > 20) {
                Toast.makeText(this, "Enter a number between 0 and 20",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            long fact = 1;

            for (int i = 1; i <= n; i++) {
                fact = fact * i;
            }

            Intent intent = new Intent(
                    MainActivity.this, MainActivity2.class);

            intent.putExtra("result", fact);
            intent.putExtra("number", n);

            startActivity(intent);
        });
    }
}
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number"
        android:layout_margin="20dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <Button
        android:id="@+id/btnFactorial"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial"
        app:layout_constraintTop_toBottomOf="@id/number"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity2.java:
```
package com.example.explicit;

import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity2 extends AppCompatActivity {

    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        result = findViewById(R.id.result);

        int n = getIntent().getIntExtra("number", 0);
        long fact = getIntent().getLongExtra("result", 1);

        result.setText(getString(R.string.factorial_result, n, fact));
    }
}
```
## activity_main2.java:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="20sp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```



## OUTPUT:
<img width="1920" height="1200" alt="Screenshot (256)" src="https://github.com/user-attachments/assets/ea78b8a0-a8ae-4e1d-b628-9a5b06029685" />
<img width="1920" height="1200" alt="Screenshot (255)" src="https://github.com/user-attachments/assets/e1d7c037-1678-480e-aa0b-c81b975d0165" />





## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


