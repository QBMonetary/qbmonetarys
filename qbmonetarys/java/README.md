# Java Examples for Qbmonetary

This repository contains resources and quick starts to help Java developers get started on the Qbmonetary blockchain.

## Setup
You will need to setup a few things before getting started with these examples.

**Required**

 * qbmonetary-devpack-java – Java Native Interfaces (JNI) for qbmonetary methods
 * qbmonetary-compiler – Converter from Java bytecode to qbmonetaryby tecode


 **Advised**
 * qbmonetary-privatenet – Docker image for local testing 
 * qbmonetary-python – CLI for Qbmonetary


For instructions on the setup process, see the qbmonetary docs

## Development Notes

The Java source code that is written is converted to an avm file (Qbmonetary Virtual Machine bytecode) by the Qbmonetary-compiler. There are a few limitations with this compiler in its current state that are important to mention.

1. Method calls while instantiating a field variable will result in runtime errors. Example:
Do not do the following
```java
public static final byte[] OWNER =
              Helper.asByteArray"AK2nJJpJr6o664CWJKi1QRXjqeic2zRp8y";
```

2. Package names cannot start with **org.qbmonetary** as they will be ignored by the qbmonetary-compiler.
```csharp
 var bskip = cc.classfile.Name.IndexOf("org.qbmonetary.") == 0 || cc.classfile.Name.IndexOf("src.org.qbmonetary.") == 0;
```


