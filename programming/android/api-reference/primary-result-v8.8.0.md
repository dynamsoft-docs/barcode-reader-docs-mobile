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
  | [`initIntermediateResult`](#initintermediateresult) | Inits an intermediateResult struct with default values. |
  | [`getIntermediateResults`](#getintermediateresults) | Get intermediate results. |
  | [`decodeIntermediateResults`](#decodeintermediateresults) | Decodes barcode from intermediate results. |
  | [`enableResultVerification`](#enableresultverification) | Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. This feature is not enabled by default. |
  | [`enableDuplicateFilter`](#enableduplicatefilter) | Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. Barcode results with the same text and format will be returned only once during the period. |

  ---

## initIntermediateResult

Inits an intermediateResult struct with default values.

```java
IntermediateResult initIntermediateResults(int resultType) throws BarcodeReaderException
```

**Parameters**

`resultType`: An int value that indicates the intermediate result type. The int value should be available in ([EnumIntermediateResultType]({{ site.mobile_enum }}intermediate-result-type.html?lang=android)).

**Return Value**

An [`IntermediateResult`](auxiliary-IntermediateResult.md) struct with default values.

**Exceptions**

A [`BarcodeReaderException`](auxiliary-BarcodeReaderException.md) is thrown when:

- Your license key doesn't include the intermediate result item.

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
IntermediateResult imResult = reader.initIntermediateResult(EnumIntermediateResultType.IRT_ORIGINAL_IMAGE);
```

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
TextResult[] result = reader.decodeFile("your file path","");
IntermediateResult[] irtResult = reader.getIntermediateResults();
```

## decodeIntermediateResults

Decodes barcode from intermediate results.

```java
TextResult[] decodeIntermediateResults(IntermediateResult[] results) throws BarcodeReaderException
```

**Parameters**

`results`: An array of intermediate result.  

**Return Value**

The [`TextResult`](auxiliary-TextResult.md) of all successfully decoded barcodes. `TextResult` includes the text, format and other information about the barcodes.

**Exceptions**

[`BarcodeReaderException`](auxiliary-BarcodeReaderException.md)

**Code Snippet**

```java
BarcodeReader reader = new BarcodeReader();
/*Init DBR license before decoding*/
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.intermediateResultTypes = EnumIntermediateResultType.IRT_ORIGINAL_IMAGE;
reader.updateRuntimeSettings(settings);
reader.decodeFile("your file path","");
IntermediateResult[] irtResult = reader.getIntermediateResults();
TextResult[] result = reader.decodeIntermediateResults(irtResult,"");
```

## enableResultVerification

Enable **Result Verification** feature to improve the accuracy of barcode results for video streaming barcode decoding. This feature is not enabled by default.

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

Enable **Duplicate Filter** feature to filter out the duplicate results in the period of 3000ms for video barcode decoding. Barcode results with the same text and format will be returned only once during the period.

There are 2 way for you to get barcode results:

- From the return value of [`decode`](primary-decode.md) methods when processing a single image.
- From the [`textResultCallback`](interface-textresultcallback.md) when processing the video streaming.

**Duplicate filter** only effects on the duplicate results that output by `textResultCallback`.

```java
void enableDuplicateFilter(boolean)
```

**Code Snippet**

```java
reader.enableDuplicateFilter(true)
```
