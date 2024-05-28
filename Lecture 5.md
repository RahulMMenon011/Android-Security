#### 1.APKtool

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/a000eeda-2e1b-46fa-8a76-27d17762599c)

Decomiplation: Trying to reach to Source Code From Executable File. Here .dex means Dalvik Executable Code Format

> apktool d .\sample.apk -o test

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/5d51446a-540d-422f-9de1-0180c6ed7ef2)

We note that the files classes.dex and resources.arsc that were previously in the ZIP file are missing from the testsample directory. We note that the directory now has an apktool.yml file created in it. Additionally, we see that a new directory named original has an additional AndroidManifest.xml file. We also see that the classes.dex file found in the original APK ZIP folder has been decompiled into a new directory named smali.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/e5067346-7591-4944-80af-e369390335bc)

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/52a096f3-4a29-4650-8178-9732895e444b)

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/22a106a6-244a-4c18-a596-b712acce28ce)

#### Now Jadx Tool

jadx is a Dex to Java decompiler. It is a command line and GUI tools for producing Java source code from Android Dex and Apk files

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/d5445d3d-3c7d-45ba-a34b-ad516679c693)

The decompiled JAVA source code is seen in the JADX window.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/39026607-8d55-4b6b-85e2-3599d6e972ff)


![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/074771e9-296f-4eb4-8e9f-b489cd10b7d7)
