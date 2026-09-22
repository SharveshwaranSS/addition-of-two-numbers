# Addition of Two Numbers

## AIM
To create a program that adds two numbers and displays the result. This demonstrates basic arithmetic operations and variable handling.

---

### Algorithm:
1. Start the program
2. Declare two variables to store the first and second numbers
3. Accept or initialize values for both numbers
4. Add the two numbers using the addition operator (+)
5. Store the result in a third variable
6. Display the result
7. End the program


---

## PROGRAM
```
/*
Program to display animation operation”.
Developed by:THAMEEZ AHMED A
Registeration Number :212224220116
*/
```
Activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:padding="16dp"
        android:gravity="center">

        <EditText
            android:id="@+id/editTextNumber1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/hint_first_number"
            android:inputType="numberDecimal"
            android:autofillHints="none" />

        <EditText
            android:id="@+id/editTextNumber2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/hint_second_number"
            android:inputType="numberDecimal"
            android:layout_marginTop="8dp"
            android:autofillHints="none" />

        <Button
            android:id="@+id/buttonAdd"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn_add"
            android:layout_marginTop="16dp" />

        <TextView
            android:id="@+id/textViewResult"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textSize="18sp"
            android:layout_marginTop="24dp" />

    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```
MainActivity.java
```
package com.example.addition;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText editTextNumber1;
    private EditText editTextNumber2;
    private TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        editTextNumber1 = findViewById(R.id.editTextNumber1);
        editTextNumber2 = findViewById(R.id.editTextNumber2);
        Button buttonAdd = findViewById(R.id.buttonAdd);
        textViewResult = findViewById(R.id.textViewResult);

        buttonAdd.setOnClickListener(v -> calculateSum());
    }

    private void calculateSum() {
        String strNum1 = editTextNumber1.getText().toString().trim();
        String strNum2 = editTextNumber2.getText().toString().trim();

        if (strNum1.isEmpty() || strNum2.isEmpty()) {
            Toast.makeText(this, getString(R.string.msg_enter_numbers), Toast.LENGTH_SHORT).show();
            return;
        }

        try {
            double num1 = Double.parseDouble(strNum1);
            double num2 = Double.parseDouble(strNum2);
            double sum = num1 + num2;

            textViewResult.setText(getString(R.string.result_format, sum));
        } catch (NumberFormatException e) {
            Toast.makeText(this, getString(R.string.msg_invalid_input), Toast.LENGTH_SHORT).show();
        }
    }
}
```



## OUTPUT
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/e554f772-cccc-4e0c-90bb-21cd8d305a13" />
<img width="1915" height="1197" alt="image" src="https://github.com/user-attachments/assets/0247559a-0113-4526-9e35-08b42db5bcb1" />
<img width="1917" height="1197" alt="image" src="https://github.com/user-attachments/assets/6f1425cd-93d0-49e3-b95d-951de254a6cd" />



## RESULT

The program successfully demonstrates the addition operation with clear input-output relationships

