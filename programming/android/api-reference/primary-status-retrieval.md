---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - BarcodeReader Status Retrieval Methods
description: This page shows BarcodeReader status retrieval methods of Dynamsoft Barcode Reader for Android SDK.
keywords: getVersion, status retrieval methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-status-retrieval.html
---

# Status Retrieval Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|

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
