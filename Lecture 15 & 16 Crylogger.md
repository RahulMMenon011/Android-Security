# Crylogger

Crylogger is a tool designed for dynamic analysis of Android applications with the primary goal of detecting cryptographic misuse. Cryptographic misuse refers to incorrect or insecure implementation of cryptographic functions which can lead to vulnerabilities, making the application susceptible to attacks. Crylogger helps identify these issues by monitoring the runtime behavior of an application.

Crylogger works by dynamically analyzing the runtime behavior of Android applications to detect cryptographic misuse

### Working

**Instrumentation** : Crylogger modifies the APK to insert hooks into cryptographic API calls.

**Execution**: The instrumented APK runs on an Android device, with Crylogger monitoring cryptographic operations.

**Logging**: Crylogger logs details of cryptographic operations, including algorithms, keys, and parameters.

**Analysis**: It analyzes the logged data to detect cryptographic misuses based on predefined patterns and rules.

**Reporting**: Crylogger generates a detailed report highlighting detected misuses and providing recommendations.

**Iteration**: Developers iterate on their code based on Crylogger's findings to enhance application security.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/8ee8c781-883d-4439-9058-6cf389fe7ef8)

```
adb shell monkey -p your.package.name -v 500 
```

For ex, as shown above frameworks and libcore can be changed accordingly to create a new android distribution and to have our emulator a different logging functionality.Likewise many changing logging functionality of the open source android OS and making it their own Android distributions

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/974f1917-38c0-4678-a425-7bb4b5f71e33)


It will make logs and specifies the analysis made upon cryptographic functionalities of the application.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/a682f354-0a72-42d6-8f16-3c37be8f6d43)


Above is the repositories that contains source codes of the released android versions and by changing the logging functionality of the desired version of android, new distribution is created on our own.
