---
layout: default-layout
title: iQRCodeDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iQRCodeDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iQRCodeDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: false
permalink: /programming/objectivec-swift/api-reference/auxiliary-iQRCodeDetails-v8.1.0.html
---


# iQRCodeDetails

Stores the QRCode details.  

## Typedefs

```objc
@interface iQRCodeDetails
```  
  
---

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *NSInteger* |
| [`rows`](#rows) | *NSInteger* |
| [`columns`](#columns) | *NSInteger* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile_enum }}qr-code-error-correction-level.html?lang=objc,swift) |
| [`version`](#version) | *NSInteger* |
| [`model`](#model) | *NSInteger* |

### moduleSize

The barcode module size (the minimum bar width in pixel).  

```objc
NSInteger moduleSize
```

### rows

The row count of the barcode.  

```objc
NSInteger rows
```

### columns

The column count of the barcode.

```objc
NSInteger columns
```

### errorCorrectionLevel

The error correction level of the barcode.

```objc
EnumQRCodeErrorCorrectionLevel errorCorrectionLevel
```

### version

The version of the QR Code.

```objc
NSInteger version
```

### model

Number of the models.

```objc
NSInteger model
```
