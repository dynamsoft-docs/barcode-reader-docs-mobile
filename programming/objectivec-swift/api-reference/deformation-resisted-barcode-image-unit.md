---
layout: default-layout
title: DSDeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDeformationResistedBarcodeImageUnit class represents a unit that contains deformation resisted barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSDeformationResistedBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDeformationResistedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/deformation-resisted-barcode-image-unit.html
---

# DSDeformationResistedBarcodeImageUnit Class

The `DSDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDeformationResistedBarcodeImageUnit: DSIntermediateResultUnit
```
2. 
```swift
class DeformationResistedBarcodeImageUnit: DSIntermediateResultUnit
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | Gets the deformation resisted barcode image data. |

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
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.enums}}/core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

### imageData

Gets the deformation resisted barcode image data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, strong, nullable) DSImageData *imageData;
```
2. 
```swift
var imageData: DSImageData? { get set }
```
