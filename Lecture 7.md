#### 7. Input Validation Issues- Part 1

We explore the application by entering values in the search EditText field

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/367fea3d-aa09-4d85-ab75-af09fe94cc4d)

We observe the decompiled source code in the JADX

![Screenshot 2024-05-29 185417](https://github.com/RahulMMenon011/Android-Security/assets/140642506/69602f4d-166a-45b8-9860-49c45d629302)

We understand that for this Task an activity called SQLInjectionActivity is used.

![Screenshot 2024-05-29 185555](https://github.com/RahulMMenon011/Android-Security/assets/140642506/e908128d-d6c6-4d39-a587-fa70af866375)

We enter `1' OR 1=1--` so that the above SQL query becomes

```sql
SELECT * FROM sqliuser WHERE user ='1' OR 1=1--'
```
The WHERE clause condition gets evaluated to FALSE or TRUE which is equivalent to TRUE, hence all the records in the database are displayed in the Toast message.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/c423e9f6-c2df-44e9-83c8-b43b00f5d3fd)

#### 8. Input Validation Issues- Part 2

We explore the application by entering values in the URL EditText field.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/6d6d4a03-9205-4e29-bd2f-8a145c74862d)

We enter a sensitive path like `file:///data/data/jakhar.aseem.diva/shared_prefs/jakhar.aseem.diva_preferences.xml`

which only the application has access to and normal user of the device does not have access to. We observe that the file contents are displayed in the WebView.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/9c1c8c7f-1059-4e58-92b0-fbfa38024922)

We observe the decompiled source code and open the InputValidation2URISchemeActivity in the JADX.

We observe that the user input value in the EditText field is used directly to load in the WebView without any sanitization or validation.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/1ab2c714-3555-440e-a862-a3512ee65304)

We observe the decompiled source code and open the InputValidation2URISchemeActivity in the JADX.

We observe that the user input value in the EditText field is used directly to load in the WebView without any sanitization or validation.

![Screenshot 2024-05-29 190740](https://github.com/RahulMMenon011/Android-Security/assets/140642506/575d7984-4d58-4ed7-8831-7b91aa09ba5e)



