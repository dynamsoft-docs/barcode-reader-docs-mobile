---
layout: default-layout
title: iTextResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iTextResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iTextResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iTextResult-v8.0.0.html
---


# iTextResult

Stores the text result.

## Typedefs

```objc
@interface iTextResult
```  
  
---

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) |
| [`barcodeFormatString_2`](#barcodeformatstring_2) | *NSString \** |
| [`barcodeText`](#barcodetext) | *NSString \** |
| [`barcodeBytes`](#barcodebytes) | *NSData \** |
| [`localizationResult`](#localizationresult) | [`iLocalizationResult`](auxiliary-iLocalizationResult.md)\* |
| [`detailedResult`](#detailedresult) | *NSObject \** |
| [`extendedResults`](#extendedresults) | [`NSArray<iExtendedResult*>*`](auxiliary-iExtendedResult.md)\* |

### barcodeFormat

Barcode type in BarcodeFormat group 1.

```objc
EnumBarcodeFormat barcodeFormat
```

### barcodeFormatString

Barcode type in BarcodeFormat group 1 as string.

```objc
NSString* barcodeFormatString
```

### barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```objc
EnumBarcodeFormat2 barcodeFormat_2
```

### barcodeFormatString_2

Barcode type in BarcodeFormat group 2 as string.

```objc
NSString* barcodeFormatString_2
```

### barcodeText

The barcode text, ends by '\0'.

```objc
NSString* barcodeText
```

### barcodeBytes

The barcode content in a byte array.

```objc
NSData* barcodeBytes
```

### localizationResult

The corresponding localization result.

```objc
iLocalizationResult* localizationResult
```

### detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md).

```objc
NSObject* detailedResult
```

### extendedResults

The extended result array.

```objc
NSArray<iExtendedResult*>* extendedResults
```
