---
layout: default-layout
title: Interface - Dynamsoft Barcode Reader Android API Reference
description: This page shows all interfaces of Dynamsoft Barcode Reader for Android SDK.
keywords: ErrorCallback, IntermediateResultCallback, TextResultCallback, DBRServerLicenseVerificationListener, interface, api reference, android
needAutoGenerateSidebar: true
permalink: /programming/android/api-reference/interface-v7.6.0.html
---

# Interface - v7.6

  | Function | Description |
  |----------|-------------|
  | [`ErrorCallback`](#errorcallback) | Represents the method that will handle the error code returned by the SDK. |
  | [`IntermediateResultCallback`](#intermediateresultcallback) | Represents the method that will handle the intermediate result array returned by the SDK. |
  | [`TextResultCallback`](#textresultcallback) | Represents the method that will handle the text result array returned by the SDK. | 
  | [`DBRServerLicenseVerificationListener`](#dbrserverlicenseverificationlistener) | Represents the method that will
   handle callback when license server returns. |
  
---

## ErrorCallback

Represents the method that will handle the error code returned by the SDK.

```java
void com.dynamsoft.barcode.ErrorCallback.errorCallback(int frameId, int errorCode, Object userData)	
```

**Parameters**

`frameId`: The ID of the frame.
`errorCode`: Error Code generated when decoding the frame.
`userData`: Arguments passed to your function.

## IntermediateResultCallback

Represents the method that will handle the intermediate result array returned by the SDK.

```java
void com.dynamsoft.barcode.IntermediateResultCallback.intermediateResultCallback(int frameId, IntermediateResult[] results, Object userData)	
```

**Parameters**

`frameId`: The ID of the frame.  
`results`: The intermediate results of the frame.
`userData`: Arguments passed to your function.

**See Also**

[IntermediateResult](auxiliary-IntermediateResult.html)

## TextResultCallback

Represents the method that will handle the error code returned by the SDK.

```java
void textResultCallback(int frameId, TextResult[] results, Object userData)
```

**Parameters**

`frameId`: The ID of the frame.  
`results`: Recognized barcode results of the frame.
`userData`: Arguments passed to your function.

**See Also**

[TextResult](auxiliary-TextResult.html)

## DBRServerLicenseVerificationListener

Represents the method that will handle the error code returned by the SDK.

```java
void com.dynamsoft.barcode.DBRServerLicenseVerificationListener.licenseVerificationCallback (boolean isSuccess, Exception error)
```

**Parameters**

`isSuccess`: Whether the license verification was successful.
`error`: The error message from license server.
