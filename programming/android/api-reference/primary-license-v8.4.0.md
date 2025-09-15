---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader license methods of Dynamsoft Barcode Reader for Android SDK.
keywords: initLicense, initLicenseFromServer, initLicenseFromLicenseContent, outputLicenseToString, license methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-license-v8.4.0.html
---


# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Read product key and activate the SDK. |
  | [`initLicenseFromServer`](#initlicensefromserver) | Initialize license and connect to the specified server for online verification. |
  | [`initLicenseFromLicenseContent`](#initlicensefromlicensecontent) | Initialize license from the license content on client machine for offline verification. |
  | [`outputLicenseToString`](#outputlicensetostring) | Output the license content to a string from the license server. |
  | [`initLicenseFromLTS`](#initlicensefromlts) | Initializes the barcode reader license and connects to the specified server for online verification. |

  ---

## initLicense

Read the product key and activate the SDK.

```java
void initLicense(String license) throws BarcodeReaderException
```

**Parameters**

`license`: The product keys.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initLicense("t0260NwAAAHV***************");
```

## initLicenseFromServer

Initialize the license and connect to the specified server for online verification.

```java
void initLicenseFromServer(String licenseServer, String licenseKey, DBRServerLicenseVerificationListener dbrServerLicenseVerificationListener)
```

**Parameters**

`licenseServer`: The URL of the license server.  
`licenseKey`: The license key.  
`dbrServerLicenseVerificationListener`: The delegate to handle callback when license server returns.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initLicenseFromServer("", "C087****",  new DBRServerLicenseVerificationListener() {
    @Override
    public void licenseVerificationCallback(boolean isSuccess, Exception error) {
    }
});
```

## initLicenseFromLicenseContent

Initialize barcode reader license from the license content on the client machine for offline verification.

```java
void initLicenseFromLicenseContent(String licenseKey, String licenseContent) throws BarcodeReaderException
```

**Parameters**

`licenseKey`: The license key.  
`licenseContent`: An encrypted string representing the license content (quota, expiration date, barcode type, etc.) obtained from the method [`OutputLicenseToString`](#outputlicensetostring).

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
//get String licenseContent from reader.outputLicenseToString();
reader.initLicenseFromLicenseContent("C087****",licenseContent);
```

## outputLicenseToString

Output the license content as an encrypted string from the license server to be used for offline license verification.

```java
String outputLicenseToString() throws BarcodeReaderException
```

**Return Value**

The output string which stores the contents of license.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Remark**

[`InitLicenseFromServer`](#initlicensefromserver) has to be successfully called before calling this method.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
reader.initLicenseFromServer("", "C087****",  new DBRServerLicenseVerificationListener() {
    @Override
    public void licenseVerificationCallback(boolean isSuccess, Exception error) {
    }
});
String licenseContent = reader.outputLicenseToString();
```

## initLicenseFromLTS

Initializes the barcode reader license and connects to the specified server for online verification.

```java
void initLicenseFromLTS(DMLTSConnectionParameters ltsInfo, DBRLTSLicenseVerificationListener listener)
```

**Parameters**

`ltsInfo`: The struct DMLTSConnectionParameters with customized settings.  
`listener`: The delegate to handle callback when license server returns.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
DMLTSConnectionParameters info = new DMLTSConnectionParameters();
info.organizationID = "200001";
info.sessionPassword = "******";
reader.initLicenseFromLTS(info, new DBRLTSLicenseVerificationListener() {
   @Override
   public void LTSLicenseVerificationCallback(boolean b, Exception e) {
      if (!b && e != null) {
         e.printStackTrace();
      }
   }
});
```
