---
layout: default-layout
title: Interface ErrorCallback - Dynamsoft Barcode Reader Android API Reference
description: This is the interface ErrorCallback page of Dynamsoft Barcode Reader for Android SDK.
keywords: ErrorCallback, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/interface-errorcallback.html
---

# ErrorCallback

`ErrorCallback` is the interface to handle callback when an error is returned when using video frame decoding.

> Note:  
>  
> - This class is removed in 9.0 version. Please use the [video methods](primary-video.md) for video barcode scanning if you are using the latest version.

```java
interface com.dynamsoft.dbr.ErrorCallback
```

| Method | Description |
| ------ | ----------- |
| `errorCallback` | Represents the method to handle the error code returned by the library. |

## errorCallback

```java
void errorCallback(int frameId, int errorCode, Object userData);
```

**Parameters**

`frameId`: The ID of the frame.  
`errorCode`: Error Code generated when decoding the frame.  
`userData`: Arguments passed to your function.

**Code Snippet**

```java
ErrorCallback errorCallback = new ErrorCallback() {
    @Override
    public void errorCallback(int frameID, int errorCode, Object userData) {
        //Add your code     
    }
};
```
