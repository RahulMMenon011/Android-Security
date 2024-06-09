# Fuzzing

Fuzzing, or fuzz testing, is an automated software testing technique used to identify vulnerabilities, bugs, and unexpected behavior in software applications.

The tools used for fuzzing are

1. **OSS-Fuzz:** Continuous Fuzzing Service for Open Source Software
2. **ClusterFuzz:** Scalable Fuzzing Infrastructure
3. **FuzzBench:** Fuzzer benchmarking as a service

Fuzzing involves testing the behavior and vulnerabilities of functions by manipulating inputs, such as strings or images.

[Fuzzing](https://github.com/google/fuzzing) Refer this for more information.

These are all common fuzzing tools, but we will be discussing the CDF (crypto differential fuzzing) tool.

##   CDF (crypto differential fuzzing)

Crypto differential fuzzing is a specialized form of fuzz testing applied to cryptographic algorithms and implementations. Its primary goal is to identify subtle vulnerabilities and bugs, particularly those related to differential properties of cryptographic functions.

Unlike general-purpose fuzzers and testing software, CDF is:

- **Smart**: CDF knows what kind of algorithm it's testing and adapts to the tested functions.
- **Fast**: CDF tests only what needs to be tested and parallelizes its tests as much as possible.
- **Polyvalent**: CDF isn't specific to any language or API, but supports arbitrary executable programs or scripts.
- **Portable**: CDF will run on any Unix or Windows platform, since it is written in Go without any platform-specific dependencies.

The purpose of CDF is to provide more efficient testing tool to developers and security researchers, being more effective than test vectors and cheaper than manual audit of formal verification.

[CDF](https://github.com/kudelskisecurity/cdf)Refer here for more information.


## INSTALLATION

![image](https://github.com/ananthan05/Android-Security/assets/140697378/6e389c52-b90e-46ae-8e64-4db65145801d)

```
git clone https://github.com/kudelskisecurity/cdf.git
```

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/2c558180-17e0-4346-93ea-bad99ef297b7)

![image](https://github.com/RahulMMenon011/Android-Security/assets/140642506/ee2d2fa7-1595-44a2-b9ed-a5c1fb583384)


## First build the cdf binary.

```
 make examples-all
```
 will build all the examples.
 
 while 
 ```
make examples-go
```
 will only build the Go examples.

```
make test
```
will run unit tests (of CDF).


you may want to view usage info by running 

```
cdf -h
```


You may then try an example such as the rsaenc interface against the RSA OAEP Go and CryptoPP examples. Viewing CryptoPP as our reference, you can test the Go implementation by doing:

```
cdf rsaenc /examples/oaep_rsa2048_go /examples/oaep_rsa2048_cryptopp
```
This command will perform various tests specific to the rsaenc interface.

>In this example, CDF should complain about the maximum public exponent size the Go implementation support: if we check its code we can see the public exponent is being stored as a normal integer, whereas in CryptoPP (and most other implementations), it is stored as a big integer. This is however by design and will likely not be changed.
