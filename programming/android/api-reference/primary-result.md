---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - BarcodeReader Result Methods
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
  | [`enableDuplicateFilter`](#enableduplicatefilter) | Filter out the duplicate results in the period of `duplicateForgetTime` for video barcode decoding. Barcode results with the same text and format will be returned only once during the period. |
  | [`setDuplicateForgetTime`](#enableresultverification) | Set the `duplicateForgetTime`. |
  | [`getDuplicateForgetTime`](#enableduplicatefilter) | Get the `duplicateForgetTime`. |

  ---

## getIntermediateResults

Get intermediate results containing the original image, the color clustered image, the binarized Image, contours, Lines, TextBlocks, etc.

```java
IntermediateResult[] getIntermediateResults() throws BarcodeReaderException 
```

**Return Value**

The [`IntermediateResult`](auxiliary-IntermediateResult.md) array were returned by the SDK.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- The library failed to get the intermediate result, which might because your license key doesn't include the intermediate result item.

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

Enable **result verification** on the barcode results of video streaming barcode decoding. This feature is not enabled by default.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Result verification** feature only effects on the **OneD barcode** results you get from `textResultCallback`.

```java
void enableResultVerification(boolean)
```

**Code Snippet**

```java
reader.enableResultVerification(true)
// To check the status of this mode:
boolean x = reader.getEnableResultVerificationStatus();
```

## enableDuplicateFilter

Filter out the duplicate results in the period of `duplicateForgetTime` for video barcode decoding. Barcode results with the same text and format will be returned only once during the period. The default value of `duplicateForgetTime` is 3000ms.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Duplicate filter** only effects on the duplicate results that output by `textResultCallback`.

```java
void enableDuplicateFilter(boolean)
```

**Code Snippet**

```java
// You can set the duration of duplicate filter.
reader.setDuplicateForgetTime(500);
reader.enableDuplicateFilter(true)
```

## setDuplicateForgetTime

Set the `duplicateForgetTime`.

```java
void setDuplicateForgetTime();
```

## getDuplicateForgetTime

Set the `duplicateForgetTime`.

```java
boolean getDuplicateForgetTime();
```
