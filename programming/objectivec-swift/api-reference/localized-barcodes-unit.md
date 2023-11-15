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

The `DSLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

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

## Inherited Attributes

The following attributes are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`hashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#hashid) | *NSString \** | The hash ID of the unit. |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagehashid) | *NSString \** | The hash ID of the original image. You can use this ID to get the original image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagetag) | *DSImageTag \** | The image tag of the original image. |
| [`type`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#type) | *DSIntermediateResultUnitType* | The type of the intermediate result unit. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.enums}}core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

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
