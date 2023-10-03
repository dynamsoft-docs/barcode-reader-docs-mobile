---
layout: default-layout
title: BarcodeReader Status Retrieval Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader status retrieval methods of Dynamsoft Barcode Reader for Android SDK.
keywords: getVersion, status retrieval methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-status-retrieval-v9.6.20.html
---

# Status Retrieval Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK. |
  | [`setLogConfig`](#setlogconfig) | Set the directory and the saving mode of log. It helps you on debugging. |

  ---

## getVersion

Get version information of SDK.

```java
static String getVersion()
```

**Return Value**

The version of `DynamsoftBarcodeReader` Android SDK and `DynamsoftBarcodeReader` algorithm.

**Code Snippet**

```java
String version = BarcodeReader.getVersion();
```

## setLogConfig

Set the directory and the saving mode of log. It helps you on debugging.

```java
void setLogConfig(String logDir, EnumLogMode mode) throws BarcodeReaderException;
```

**Parameters**

`[in] logDir`: Where to save the log.  
`[in] mode`: The saving mode of the log.

**Exception**

An exception is thrown when the directory you input is invalid.

**Return Value**

A boolean value that indicates whether the log config is approved.

```java
try {
   BarcodeReader.setLogConfig("The path of the directory", EnumLogMode.LM_TEXT);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```
