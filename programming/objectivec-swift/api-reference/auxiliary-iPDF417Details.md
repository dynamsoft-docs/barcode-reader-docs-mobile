---
layout: default-layout
title: iPDF417Details Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iPDF417Details Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iPDF417Details, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iPDF417Details.html
---


# Class iPDF417Details

`iPDF417Details` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the PDF417 code details.

```objc
@interface iPDF417Details
```  

| Attribute | Type | Descriptions |
|---------- |------|------------ |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](#columns) | *NSInteger* | The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *NSInteger* | The error correction level of the barcode. |
| [`hasLeftRowIndicator`] | *int* | Indicates whether the PDF417 barcode has a left row indicator. |
| [`hasRightRowIndicator`] | *int* | Indicates whether the PDF417 barcode has a right row indicator. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```objc
@property (nonatomic, assign) NSInteger moduleSize
```

## rows

The row count of the barcode.

```objc
@property (nonatomic, assign) NSInteger rows
```

## columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```objc
@property (nonatomic, assign) NSInteger columns
```

## errorCorrectionLevel

The error correction level of the barcode.

```objc
@property (nonatomic, assign) NSInteger errorCorrectionLevel
```

## hasLeftRowIndicator

Indicates whether the PDF417 barcode has a left row indicator.

```objc
@property (nonatomic, assign) NSInteger hasLeftRowIndicator
```

## hasRightRowIndicator

Indicates whether the PDF417 barcode has a right row indicator.

```objc
@property (nonatomic, assign) NSInteger hasRightRowIndicator
```
