---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Interface TextResultListener
description: This the interface TextResultListener page of Dynamsoft Barcode Reader for Android SDK.
keywords: TextResultListener, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/interface-textresultcallback.html
---

# TextResultListener

`TextResultListener` is the interface to handle callbacks when the barcode results are returned.

```java
interface com.dynamsoft.dbr.TextResultListener
```

| Method | Description |
| ------ | ----------- |
| `textResultCallback` | Represents the method to handle the text result array returned by the library. |

## textResultCallback

Represents the method to handle the text result array returned by the library.

```java
void textResultCallback(int frameId, ImageData imageData, TextResult[] results);
```

**Parameters**

`frameId`: The ID of the frame.  
`imageData`: The image data of the frame.  
`results`: Recognized barcode results of the frame.

**Code Snippet**

**Code Snippet**

You have to either use `CameraEnhacner` or `ImageSource` as the source of video streaming to receive barcode results from `textResultCallback`.

- View code snippet for how to get results when using [`CameraEnhancer`](primary-video.md#setcameraenhancer)
- View code snippet for how to get results when using [`ImageSource`](primary-video.md#setimagesource)

