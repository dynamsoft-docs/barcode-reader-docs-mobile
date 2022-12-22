---
layout: default-layout
title: iAztecDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iAztecDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iAztecDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iAztecDetails.html
---


# Class iAztecDetails

`iAztecDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the Aztec code details.

```objc
@interface iAztecDetails
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](#columns) | *NSInteger* | The column count of the barcode. |
| [`layerNumber`](#layernumber) | *NSInteger* | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

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

The column count of the barcode.

```objc
@property (nonatomic, assign) NSInteger columns
```  

## layerNumber

A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code.  

```objc
@property (nonatomic, assign) NSInteger layerNumber
```  
