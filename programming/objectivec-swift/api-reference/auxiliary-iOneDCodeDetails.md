---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iOneDCodeDetails Class
description: This page shows the iOneDCodeDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOneDCodeDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iOneDCodeDetails.html
---

# Class iOneDCodeDetails

`iOneDCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the OneD code details.

```objc
@interface iOneDCodeDetails
```  

| Attribute | Type | Descriptions |
|---------- |-----| ---- |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](#startcharsbytes) | *NSData \** | The start chars in a byte array. |
| [`stopCharsBytes`](#stopcharsbytes) | *NSData \** | The stop chars in a byte array. |
| [`checkDigitBytes`](#checkdigitbytes) | *NSData \** | The check digit chars in a byte array. |
| [`startPatternRange`](#startcharsbytes) | *NSData \** | The position of the start pattern relative to the barcode location. |
| [`middlePatternRange`](#stopcharsbytes) | *NSData \** | The position of the middle pattern relative to the barcode location. |
| [`endPatternRange`](#checkdigitbytes) | *NSData \** | The position of the end pattern relative to the barcode location. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```objc
@property (nonatomic, assign) NSInteger moduleSize;
```

## startCharsBytes

The start chars in a byte array.

```objc
@property (nonatomic, nullable) NSData* startCharsBytes;
```

## stopCharsBytes

The stop chars in a byte array.

```objc
@property (nonatomic, nullable) NSData* stopCharsBytes;
```

## checkDigitBytes

The check digit chars in a byte array.

```objc
@property (nonatomic, nullable) NSData* checkDigitBytes;
```

## startPatternRange

The position of the start pattern relative to the barcode location.

```objc
@property (nonatomic, nonnull) NSArray* startPatternRange;
```

## middlePatternRange

The position of the middle pattern relative to the barcode location

```objc
@property (nonatomic, nonnull) NSArray* middlePatternRange;
```

## endPatternRange

The position of the end pattern relative to the barcode location.

```objc
@property (nonatomic, nonnull) NSArray* endPatternRange;
```
