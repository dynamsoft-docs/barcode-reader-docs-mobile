---
layout: default-layout
title: DSComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSComplementedBarcodeImageUnit class represents a unit that contains complemented barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSComplementedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/complemented-barcode-image-unit-v10.0.21.html
---

# DSComplementedBarcodeImageUnit Class

The `DSComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSComplementedBarcodeImageUnit : DSIntermediateResultUnit
```
2. 
```swift
class ComplementedBarcodeImageUnit : IntermediateResultUnit
```

## Attributes

| Attributes    | Type | Description |
|---------------|------|-------------|
| [`imageData`](#imagedata) | *DSImageData \** | The image data of the complemented barcode. |
| [`location`](#location) | *DSQuadrilateral \** | The location of the result as a DSQuadrilateral object. |

## Inherited Attributes

The following attributes are inherited from the class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`hashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#hashid) | *NSString \** | The hash ID of the unit. |
| [`originalImageHashId`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagehashid) | *NSString \** | The hash ID of the original image. You can use this ID to get the original image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`originalImageTag`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#originalimagetag) | *DSImageTag \** | The image tag of the original image. |
| [`type`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#type) | *DSIntermediateResultUnitType* | The type of the intermediate result unit. |

## Inherited Methods

The following methods are inherited from the class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`getTransformMatrix`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`DSTransformMatrixType`]({{site.dcv_enumerations}}core/transform-matrix-type.html). |
| [`clone`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |

### imageData

The image data of the complemented barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable) DSImageData *imageData;
```
2. 
```swift
var imageData: ImageData? { get set }
```

### location

The location of the result as a DSQuadrilateral object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable) DSQuadrilateral *location;
```
2. 
```swift
var location: Quadrilateral? { get set }
```
