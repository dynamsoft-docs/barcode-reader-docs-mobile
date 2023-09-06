---
layout: default-layout
title: DSDecodedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DSDecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-unit.html
---

# DSDecodedBarcodesUnit Class

The `DSDecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_SWIFT_NAME(DecodedBarcodesUnit)
@interface DSDecodedBarcodesUnit: DSIntermediateResultUnit
```
2. 
```swift
class DecodedBarcodesUnit: DSIntermediateResultUnit
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`decodedBarcodes`](#decodedbarcodes) | *NSArray\<DSDecodedBarcodeElement\*> \** | Get all the barcodes that are decoded from the image. |

### decodedBarcodes

Get all the barcodes that are decoded from the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSArray<DSDecodedBarcodeElement*>* decodedBarcodes;
```
2. 
```swift
var decodedBarcodes: [DSDecodedBarcodeElement]? { get }
```
