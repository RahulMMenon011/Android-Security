We install the apk to emulator by using the command

`adb install diva-beta.apk`

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/e204c52d-9515-4159-b427-f4fb2998d030)

#### 1. Insecure Logging

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/3e072189-8445-4d81-b68e-b69b34a3cf27)

We click on Insecure logging in diva-beta app

Enter a number and click checkout

We can see an error occured notification

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/54042506-eea3-4e5f-8211-ffc37d5f26b5)

We open diva-beta.apk in JADX file

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/4cb13b34-7d47-40b5-aeb9-39007d88be1a)

#### 2.Hardcoding Issues - Part 1

We open the hardcoded activity in the JADX

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/3427fa2a-0ede-42f1-9f91-20573cf659b2)

We type the hardcoded secret key in EditText field to gain access

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/1e0cc3d6-baf4-494b-8178-78ea191fcdde)

#### 3.Insecure Data Storage Part 1

We explore app by entering username and password in EditText field

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/202855dc-cc1c-4ec6-921d-902bd2036cd5)

we use adb shell to explore the system

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/cccf35d4-7509-4a25-ac9f-d7687d991178)

inside the `/data/data/jakhar.aseem.diva` directory we can see `shareda_prefs` and `databases`

We type `cat shared_prefs/jakhar.aseem.diva_preferences.xml` to see the username and password that
were saved by the application

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/a4139fa7-81d0-4858-b862-1f67a9e06d34)

We observe the decompiled source code and open the InsecureDataStorage1Activity in the JADX.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/958f93a1-d81a-4485-ba28-cac24c6c3f31)

#### 4. Insecure Data Storage - Part 2

We explore the application by entering username and password in the EditText field

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/5e95164d-f9e7-4dc6-8fa8-8ab4f6f81e94)

We use adb shell to explore the file system used by the application.

Inside the /data/data/jakhar.aseem.diva directory, we notice the databases and shared_prefs directory.

We observe that there is a new file inside the databases directory

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/c452912d-22f3-4f90-99e7-b62d333dec52)

We open the ids2 database using the sqlite3 program, and enter select * from myuser; to view the
saved username and password.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/3c61410f-4e07-455a-8491-b8d9e4519f18)

We observe the decompiled source code and open the InsecureDataStorage2Activity in the JADX.

![Screenshot 2024-05-29 102856](https://github.com/RahulMMenon011/Android-Security/assets/140642506/e96eed43-614f-4c0e-86a7-4b5ec99b1005)

#### 5. Insecure Data Storage - Part 3

We explore the application by entering username and password in the EditText field.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/66f4028e-c2e5-4b7f-a7eb-292ca3e963da)

We use adb shell to explore the file system used by the application.

Inside the /data/data/jakhar.aseem.diva directory, we observe that there is a new file with the name

uinfo6094420401457483314tmp We display the contents of the file using the cat uinfo6094420401457483314tmp command.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/6bd4ef62-c199-4c75-88ea-0a6cbc48664d)

We observe the decompiled source code and open the InsecureDataStorage3Activity in the JADX

![Screenshot 2024-05-29 103458](https://github.com/RahulMMenon011/Android-Security/assets/140642506/db8129de-1514-4b92-bcb5-8308fb274be4)

#### 6. Insecure Data Storage - Part 4

We explore the application by entering username and password in the EditText field.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/f1df5709-53f6-497b-9e31-8af37f5aa08e)

We observe the decompiled source code and open the InsecureDataStorage4Activity in the JADX.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/5394f609-fc28-4a88-8dae-a9aeb8506488)

In the adb shell, we navigate to cd /sdcard and type the commands: ls -a and cat .uinfo.txt to view
the contents of the file.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/c918d254-3aaa-4c8c-a582-86815406cee9)

