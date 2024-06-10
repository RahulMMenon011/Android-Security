# Android Keystore and Key Signing

The Android Keystore and key signing are essential components in ensuring the security and integrity of Android applications. The Android Keystore System allows developers to securely store cryptographic keys in a way that makes them less susceptible to extraction and misuse.

## Common Operations

### Generating Keys
You can generate asymmetric (RSA, EC) and symmetric (AES) keys.

### Using Keys
Keys can be used for various operations like encryption, decryption, signing, and verification.

### Storing and Retrieving Keys
Once generated, keys can be stored and later retrieved for cryptographic operations.

## Key Generation:

```
keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
```

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/59b8439b-fa9f-42e6-a25c-091ffccdcb54)


![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/2da4c9bf-9f86-49fd-999c-aebe45b271f2)



## Key Signing

Key signing is a crucial process in Android development that ensures the authenticity and integrity of an APK file. Each APK must be signed with a certificate before it can be installed on a device.

### Key Components

- **Signing Keys**: The private key used to sign the APK, which must be kept secure.
- **Certificates**: The public key certificate corresponding to the signing key, embedded in the APK, allows users to verify the source of the application.

### Tools Used

#### Jarsigner
- Used to sign Java ARchive (JAR) files, including APKs.
- Signs the APK file using the private key from the keystore.

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/c7e35b7e-6b74-49c0-b475-645f1e7b8dee)


![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/7e837a79-76f2-48b5-b202-25b4fd106c4a)



#### APK Signature Scheme v2 and v3
- Enhances security by providing stronger guarantees that the APK hasn't been tampered with.
- The newer Android versions (7.0 and above) use APK Signature Scheme v2 or v3, which offers additional protections compared to the original JAR signing.

### Verifying a Signed JAR/APK File

To verify that a JAR or APK file has been correctly signed and has not been tampered with, use:

```sh
jarsigner -verify -verbose -certs my-application.apk
```
