---
layout: default-layout
title: iTextResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iTextResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iTextResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iTextResult-v8.6.0.html
---

# Class iTextResult

Stores the text result data.

```objc
@interface iTextResult
```  

| Attribute | Type | Description |
|-----------|------| ----------- |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](#barcodeformatstring_2) | *NSString \** | Barcode type in BarcodeFormat group 2 as string. |
| [`barcodeText`](#barcodetext) | *NSString \** | The barcode text, ends by '\0'. |
| [`barcodeBytes`](#barcodebytes) | *NSData \** | The barcode content in a byte array. |
| [`localizationResult`](#localizationresult) | [`iLocalizationResult`](auxiliary-iLocalizationResult.html) | The corresponding localization result. |
| [`detailedResult`](#detailedresult) | *NSObject \** | One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html). |
| [`extendedResults`](#extendedresults) | [`NSArray<iExtendedResult>`](auxiliary-iExtendedResult.html) | The extended result array. |
| [`exception`](#exception) | *NSString \** | The exception message. |

`iTextResultEx` is the Extension of the `iTextResult`.

```objc
@interface iTextResultEx
```

| Attribute | Type | Description |
|-----------|------| ----------- |
| [`isDPM`](#isdpm) | *NSInteger* | This attribute stands for whether the result is a DPM result. |
| [`isMirrored`](#ismirrored) | *NSInteger* | This attribute stands for whether the barcode is mirrored. |

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

## barcodeText

The barcode text, ends by '\0'.

```objc
NSString* barcodeText
```

## barcodeBytes

The barcode content in a byte array.

```objc
NSData* barcodeBytes
```

## localizationResult

The corresponding localization result.

```objc
iLocalizationResult* localizationResult
```

## detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.html), [`iPDF417Details`](auxiliary-iPDF417Details.html), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.html), [`iAztecDetails`](auxiliary-iAztecDetails.html), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.html).

```objc
NSObject* detailedResult
```

## extendedResults

The extended result array.

```objc
NSArray<iExtendedResult*>* extendedResults
```

## exception

The exception message.

```objc
NSString* exception
```

## isDPM

This attribute stands for whether the result is a DPM result.

```objc
NSInteger isDPM
```

## isMirrored

This attribute stands for whether the barcode is mirrored.

```objc
NSInteger isMirrored
```
