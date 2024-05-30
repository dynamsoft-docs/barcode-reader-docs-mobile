---
layout: default-layout
title: DSScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSScaledUpBarcodeImageUnit class represents a unit that contains scaled up barcode image. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSScaledUpBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/scaled-up-barcode-image-unit-v10.0.21.html
---

# DSScaledUpBarcodeImageUnit Class

The `DSScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSScaledUpBarcodeImageUnit: DSIntermediateResultUnit
```
2. 
```swift
class ScaledUpBarcodeImageUnit: DSIntermediateResultUnit
```

## Methods & Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | The up-scaled barcode image. |

The following attributes are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`hashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#hashid) | *NSString \** | The hash ID of the unit. |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagehashid) | *NSString \** | The hash ID of the original image. You can use this ID to get the original image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagetag) | *DSImageTag \** | The image tag of the original image. |
| [`type`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#type) | *DSIntermediateResultUnitType* | The type of the intermediate result unit. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.dcv_enumerations}}core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

### imageData

The up-scaled barcode image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong) DSImageData *imageData;
```
2. 
```swift
var imageData: DSImageData? { get set }
```
