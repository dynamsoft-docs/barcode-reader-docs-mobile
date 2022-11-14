---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Interface IntermediateResultCallback
description: This the interface IntermediateResultCallback page of Dynamsoft Barcode Reader for Android SDK.
keywords: IntermediateResultCallback, interface, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/interface-intermediateresultcallback-v8.9.3.html
---

# IntermediateResultCallback

`IntermediateResultCallback` is the interface to handle callback when intermediate results are returned.

```java
interface com.dynamsoft.dbr.IntermediateResultCallback
```

| Method | Description |
| ------ | ----------- |
| `intermediateResultCallback` | Represents the method to handle the intermediate result array returned by the library. |

## intermediateResultCallback

The abstract class for users to get intermediate results from the callback.

```java
void intermediateResultCallback(int frameId, TextResult[] results, Object userData);
```

**Parameters**

`frameId`: The ID of the frame.  
`results`: The intermediate result of the frame.  
`userData`: Arguments passed to your function.

**Code Snippet**

```java
IntermediateResultCallback intermediateResultCallback = new IntermediateResultCallback() {
    @Override
    public void intermediateResultCallback(int frameId, IntermediateResult[] results, Object userData) {
        // Add your code
    }
};
```
