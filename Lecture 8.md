## 9.ACCESS CONTROL ISSUES - PART 1

We explore the application by entering values in the search EditText field

![image](https://github.com/ananthan05/Android-Security/assets/140697378/38b8f8a7-eb23-4a45-8001-157e05806d81)

by pressing `view API CREDENTIALS`

![image](https://github.com/ananthan05/Android-Security/assets/140697378/3c25ec7f-05e0-4d64-8302-f0beef0703e2)

Our aim is without any userinteraction we need acces that `API CREDENTIALS`

When we open the adb logcat and click on the button, we can find the activity name. 
Command

```
logcat | grep -i “APICredActivity”
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/1543bc72-2ca3-44ec-b027-fb3a1e242b76)

So we run the following command:

```
adb shell am start –n jakhar.aseem.diva/.APICredsActivity
```

and confirm that when we run the following command with the device on the screen with the button.And it automatically shows the screen with the credentials without restrictions, like we had pressed the button.
