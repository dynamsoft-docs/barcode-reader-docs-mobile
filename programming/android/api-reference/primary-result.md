---
layout: default-layout
title: BarcodeReader Result Methods - Dynamsoft Barcode Reader Android API Reference
description: This page shows BarcodeReader result methods of Dynamsoft Barcode Reader for Android SDK.
keywords: getIntermediateResults, result methods, BarcodeReader, api reference, android
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/android/api-reference/primary-result.html
---

# Result Methods

  | Method               | Description |
  | -------------------- | ----------- |
  | [`getIntermediateResults`](#getintermediateresults) | Get intermediate results. |
  | [`enableResultVerification`](#enableresultverification) | Result will be verified before output. |
  | [`enableDuplicateFilter`](#enableduplicatefilter) | Duplicate results will be filtered and output only once for every 3 seconds |

  ---

## getIntermediateResults

Get intermediate results containing the original image, the color clustered image, the binarized Image, contours, Lines, TextBlocks, etc.

```java
IntermediateResult[] getIntermediateResults() throws BarcodeReaderException 
```

**Return Value**

The [`IntermediateResult`](auxiliary-IntermediateResult.md) array were returned by the SDK.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CLUSTERED_IMAGE | EnumIntermediateResultType.IRT_COLOUR_CONVERTED_GRAYSCALE_IMAGE;
reader.updateRuntimeSettings(settings);
TextResult[] result = reader.decodeFile("your file path", "");
IntermediateResult[] irtResult = reader.getIntermediateResults();
```

## enableResultVerification

The text results will be verified before output if the result verification is enabled.

>Note:
>
>- Result verification is not enabled by default.
>- Result verification only take effects on oneD barcodes.

```java
void enableResultVerification(boolean) throws BarcodeReaderException 
```

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
reader.enableResultVerification(true)
// To check the status of this mode:
boolean x = reader.getEnableResultVerificationStatus();
```

## enableDuplicateFilter

The duplicated text result will be filtered. The barcode reader will not output the result for the same barcode a second time in 3 seconds.

>Note:
>Duplicate filter is not enabled by default.

```java
void enableDuplicateFilter(boolean) throws BarcodeReaderException
```

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
reader.enableDuplicateFilter(true)
// To check the status of this mode:
boolean x = reader.getEnableDuplicateFilterStatus();
```