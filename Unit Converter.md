### Unit Converter

#### Android Manifest.html

```js
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.UnitConverter"
        tools:targetApi="31">
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
#### MainActivity.java

```js
package com.example.unitconverter;

import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Spinner;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText inputValue;
    private Spinner fromUnitSpinner, toUnitSpinner;
    private TextView resultTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        inputValue = findViewById(R.id.inputValue);
        fromUnitSpinner = findViewById(R.id.fromUnitSpinner);
        toUnitSpinner = findViewById(R.id.toUnitSpinner);
        Button convertButton = findViewById(R.id.convertButton);
        resultTextView = findViewById(R.id.resultTextView);

        String[] units = {"Celsius", "Fahrenheit", "Kelvin", "Meter", "Kilometer", "Centimeter", "Millimeter", "Gram", "Kilogram", "Pound", "Second", "Minute", "Hour"};

        ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_spinner_item, units);
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);

        fromUnitSpinner.setAdapter(adapter);
        toUnitSpinner.setAdapter(adapter);

        convertButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                convertUnits();
            }
        });
    }

    private void convertUnits() {
        String input = inputValue.getText().toString();
        if (input.isEmpty()) {
            resultTextView.setText("Please enter a value");
            return;
        }

        double value = Double.parseDouble(input);
        String fromUnit = fromUnitSpinner.getSelectedItem().toString();
        String toUnit = toUnitSpinner.getSelectedItem().toString();
        String result = "";

        switch (fromUnit) {
            case "Celsius":
                result = convertFromCelsius(value, toUnit);
                break;
            case "Fahrenheit":
                result = convertFromFahrenheit(value, toUnit);
                break;
            case "Kelvin":
                result = convertFromKelvin(value, toUnit);
                break;
            case "Meter":
                result = convertFromMeter(value, toUnit);
                break;
            case "Kilometer":
                result = convertFromKilometer(value, toUnit);
                break;
            case "Centimeter":
                result = convertFromCentimeter(value, toUnit);
                break;
            case "Millimeter":
                result = convertFromMillimeter(value, toUnit);
                break;
            case "Gram":
                result = convertFromGram(value, toUnit);
                break;
            case "Kilogram":
                result = convertFromKilogram(value, toUnit);
                break;
            case "Pound":
                result = convertFromPound(value, toUnit);
                break;
            case "Second":
                result = convertFromSecond(value, toUnit);
                break;
            case "Minute":
                result = convertFromMinute(value, toUnit);
                break;
            case "Hour":
                result = convertFromHour(value, toUnit);
                break;
            default:
                result = "Error select correct option";
        }

        resultTextView.setText(result);
    }

    private String convertFromCelsius(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Fahrenheit":
                result = (value * 9 / 5) + 32;
                break;
            case "Kelvin":
                result = value + 273.15;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromFahrenheit(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Celsius":
                result = (value - 32) * 5 / 9;
                break;
            case "Kelvin":
                result = (value - 32) * 5 / 9 + 273.15;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromKelvin(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Celsius":
                result = value - 273.15;
                break;
            case "Fahrenheit":
                result = (value - 273.15) * 9 / 5 + 32;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromMeter(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Kilometer":
                result = value / 1000;
                break;
            case "Centimeter":
                result = value * 100;
                break;
            case "Millimeter":
                result = value * 1000;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromKilometer(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Meter":
                result = value * 1000;
                break;
            case "Centimeter":
                result = value * 100000;
                break;
            case "Millimeter":
                result = value * 1000000;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromCentimeter(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Meter":
                result = value / 100;
                break;
            case "Kilometer":
                result = value / 100000;
                break;
            case "Millimeter":
                result = value * 10;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromMillimeter(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Meter":
                result = value / 1000;
                break;
            case "Kilometer":
                result = value / 1000000;
                break;
            case "Centimeter":
                result = value / 10;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromGram(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Kilogram":
                result = value / 1000;
                break;
            case "Pound":
                result = value * 0.00220462;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromKilogram(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Gram":
                result = value * 1000;
                break;
            case "Pound":
                result = value * 2.20462;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromPound(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Gram":
                result = value / 0.00220462;
                break;
            case "Kilogram":
                result = value / 2.20462;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromSecond(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Minute":
                result = value / 60;
                break;
            case "Hour":
                result = value / 3600;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromMinute(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Second":
                result = value * 60;
                break;
            case "Hour":
                result = value / 60;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }

    private String convertFromHour(double value, String toUnit) {
        double result;
        switch (toUnit) {
            case "Second":
                result = value * 3600;
                break;
            case "Minute":
                result = value * 60;
                break;
            default:
                return "Error select correct option";
        }
        return String.valueOf(result);
    }
}
```
Converting temperature

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/7c0b772b-5e0b-42eb-9e43-29b14540c5bc)

Convering Length

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/5f4a2820-718f-4e7b-8370-fa4acf4a1eeb)
