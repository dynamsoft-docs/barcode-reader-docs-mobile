---
layout: default-layout
title: DSDecodedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DSDecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-unit-v10.0.21.html
---

# DSDecodedBarcodesUnit Class

The `DSDecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

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
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.dcv_enumerations}}core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

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
