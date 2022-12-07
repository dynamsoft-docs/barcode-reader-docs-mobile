---
layout: default-layout
title: BarcodeReader License Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader license methods of Dynamsoft Barcode Reader for Android SDK.
keywords: initLicense, initLicenseFromServer, initLicenseFromLicenseContent, outputLicenseToString, license methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
pageStartVer: 8.6
permalink: /programming/android/api-reference/primary-license.html
---


# License Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`initLicense`](#initlicense) | Read product key and activate the SDK. |
  | [`setDeviceFriendlyName`](#setdevicefriendlyname) | Sets a human-readable name that identifies the device. |

  ---

## initLicense

Read the product key and activate the SDK.

```java
static void initLicense(String license, DBRLicenseVerificationListener listener)
```

**Parameters**

`license`: The product keys.
`listener`: The listener that handles callback when the license verification message is returned by the license server. See also [`DBRLicenseVerificationListener`](interface-dbrlicenseverificationlistener.md).

**Code Snippet**

```java
BarcodeReader.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", new DBRLicenseVerificationListener() {
   @Override
   public void DBRLicenseVerificationCallback(boolean isSuccess, Exception error) {
      if(!isSuccess){
         error.printStackTrace();
      }
   }
});
```

## setDeviceFriendlyName

Sets a human-readable name that identifies the device. This name will appear in the device details table when you check the statistics of the according license.

```java
static void setDeviceFriendlyName(String name) throws BarcodeReaderException
```

**Parameters**

`name` The user-defined device name.  

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
try {
   BarcodeReader.setDeviceFriendlyName("Set a name for your device.");
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```
