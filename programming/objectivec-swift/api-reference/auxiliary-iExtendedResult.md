---
layout: default-layout
title: iExtendedResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iExtendedResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iExtendedResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iExtendedResult.html
---

# Class iExtendedResult

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.md). It stores the extended result information.

```objc
@interface iExtendedResult
```  

| Attribute | Type | Descriptions |
|---------- |------|-------------|
| [`resultType`](#resulttype) | [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift) | The extended result type. |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type as string. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](#bytes) | *NSData \** | The content in a byte array. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`deformation`](#deformation) | *NSInteger* | The deformation value. |
| [`detailedResult`](#detailedresult) | *NSObject \** | One of the following: [`QRCodeDetails`](auxiliary-iQRCodeDetails.md), [`PDF417Details`](auxiliary-iPDF417Details.md), [`DataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`AztecDetails`](auxiliary-iAztecDetails.md), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.md). |
| [`samplingImage`](#samplingimage) | [`iSamplingImageData*`](auxiliary-iSamplingImageData.md) | The sampling image info. |
| [`clarity`](#clarity) | *NSInteger* | The clarity of the barcode zone in percentage. |

## resultType

Extended result type.

```objc
@property (nonatomic, assign) EnumResultType resultType
```

## barcodeFormat

Barcode type in BarcodeFormat group 1.

```objc
@property (nonatomic, assign) EnumBarcodeFormat barcodeFormat
```

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```objc
@property (nonatomic, assign) EnumBarcodeFormat2 barcodeFormat_2
```

## barcodeFormatString

Barcode type as string.

```objc
@property (nonatomic, nullable) NSString* barcodeFormatString
```

## confidence

The confidence of the result.

```objc
@property (nonatomic, assign) NSInteger confidence
```

## bytes

The content in a byte array.

```objc
@property (nonatomic, nullable) NSData* bytes
```

## accompanyingTextBytes

The accompanying text content in a byte array.

```objc
@property (nonatomic, nullable) NSData* accompanyingTextBytes
```

## accompanyingTextBytesLength

The length of the accompanying text byte array.

```objc
@property (nonatomic, nullable) NSInteger accompanyingTextBytesLength
```

## deformation

The deformation value.

```objc
@property (nonatomic, assign) NSInteger deformation
```

## detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md).

```objc
@property (nonatomic, nullable) NSObject* detailedResult
```

## samplingImage

The sampling image info.

```objc
@property (nonatomic, nullable) iSamplingImageData* samplingImage
```

## clarity

The clarity of the barcode zone in percentage.

```objc
@property (nonatomic, assign) NSInteger clarity
```
