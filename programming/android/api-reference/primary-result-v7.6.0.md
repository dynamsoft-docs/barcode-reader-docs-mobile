---
layout: default-layout
title: BarcodeReader Result Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader result methods of Dynamsoft Barcode Reader for Android SDK.
keywords: getIntermediateResults, result methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
permalink: /programming/android/api-reference/primary-result-v7.6.0.html
---


# Android API Reference - BarcodeReader Result Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getIntermediateResults`](#getintermediateresults) | Get intermediate results. |

  ---

## getIntermediateResults

Get intermediate results containing the original image, the colour clustered image, the binarized Image, contours, Lines, TextBlocks, etc.

```java
IntermediateResult[] com.dynamsoft.barcode.BarcodeReader.getIntermediateResults() throws BarcodeReaderException 
```

**Return value**

The intermediate results returned by the SDK.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.html)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader("t0260NwAAAHV***************");
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CLUSTERED_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE;
reader.updateRuntimeSettings(settings);
TextResult[] result = reader.decodeFile("your file path", "");
IntermediateResult[] irtResult = reader.getIntermediateResults();
```
