---
layout: default-layout
title: iExtendedResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iExtendedResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iExtendedResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iExtendedResult-v9.2.13.html
---

# Class iExtendedResult

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.html). It stores the extended result information.

```objc
@interface iExtendedResult
```  

| Attribute | Type | Descriptions |
|---------- |------|-------------|
| [`resultType`](#resulttype) | [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift) | The extended result type. |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](#bytes) | *NSData \** | The content in a byte array. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`deformation`](#deformation) | *NSInteger* | The deformation value. |
| [`detailedResult`](#detailedresult) | *NSObject \** | One of the following: [`QRCodeDetails`](auxiliary-iQRCodeDetails.html), [`PDF417Details`](auxiliary-iPDF417Details.html), [`DataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`AztecDetails`](auxiliary-iAztecDetails.html), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`samplingImage`](#samplingimage) | [`iSamplingImageData*`](auxiliary-iSamplingImageData.html) | The sampling image info. |
| [`clarity`](#clarity) | *NSInteger* | The clarity of the barcode zone in percentage. |

## resultType

Extended result type.

```objc
EnumResultType resultType
```

## barcodeFormat

Barcode type in BarcodeFormat group 1.

```objc
EnumBarcodeFormat barcodeFormat
```

## barcodeFormatString

Barcode type in BarcodeFormat group 1 as string.

```objc
NSString* barcodeFormatString
```

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```objc
EnumBarcodeFormat2 barcodeFormat_2
```

## barcodeFormatString_2

Barcode type in BarcodeFormat group 2 as string.

```objc
NSString* barcodeFormatString_2
```

## confidence

The confidence of the result.

```objc
NSInteger confidence
```

## bytes

The content in a byte array.

```objc
NSData* bytes
```

## accompanyingTextBytes

The accompanying text content in a byte array.

```objc
NSData* accompanyingTextBytes
```

## accompanyingTextBytesLength

The length of the accompanying text byte array.

```objc
NSInteger accompanyingTextBytesLength
```

## deformation

The deformation value.

```objc
NSInteger deformation
```

## detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html).

```objc
NSObject* detailedResult
```

## samplingImage

The sampling image info.

```objc
iSamplingImageData* samplingImage
```

## clarity

The clarity of the barcode zone in percentage.

```objc
NSInteger clarity
```
