# Dynamic Analysis Tool - Crylogger

CRYLOGGER detects cryptographic (crypto) misuses in Android apps. A crypto misuse is an invocation to a crypto API that does not respect common security guidelines, such as those suggested by cryptographers or organizations.CRYLOGGER detects crypto misuses for you automatically, without requiring to analyze a single line of your code. First, CRYLOGGER runs your Android app on the official Android Emulator.CRYLOGGER runs your app by using Monkey or the user-interface events you send to the emulator.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/0d935c1b-82de-4b2c-97c2-e7d01bcfa27d)

> adb shell monkey -p your.package.name -v 500 

For ex, as shown above frameworks and libcore can be changed accordingly to create a new android distribution and to have our emulator a different logging functionality.Likewise many changing logging functionality of the open source android OS and making it their own Android distributions

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/bf2771dc-1399-483c-9f27-0f895081e8da)


It will make logs and specifies the analysis made upon cryptographic functionalities of the application.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/0edd0822-0e93-4f55-bd27-112cf8fd7b08)

Above is the repositories that contains source codes of the released android versions and by changing the logging functionality of the desired version of android, new distribution is created on our own.
