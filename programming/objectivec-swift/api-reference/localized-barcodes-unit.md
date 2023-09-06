---
layout: default-layout
title: DSLocalizedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodesUnit class represents a unit that contains localized barcodes unit. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, DSLocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSLocalizedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/localized-barcodes-unit.html
---

# DSLocalizedBarcodesUnit Class

The `DSLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSLocalizedBarcodesUnit: DSIntermediateResultUnit
```
2. 
```swift
class LocalizedBarcodesUnit : DSIntermediateResultUnit
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`localizedBarcodes`](#localizedbarcodes) | *NSArray<DSLocalizedBarcodeElement*> \** |An array of DSLocalizedBarcodeElement. Each DSLocalizedBarcodeElement stores the information of a single localized barcode. |

### localizedBarcodes

An array of DSLocalizedBarcodeElement. Each DSLocalizedBarcodeElement stores the information of a single localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSArray<DSLocalizedBarcodeElement*>* localizedBarcodes;
```
2. 
```swift
var localizedBarcodes: [DSLocalizedBarcodeElement]? { get set }
```
