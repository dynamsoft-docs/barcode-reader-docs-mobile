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

The `DSDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `DSIntermediateResultUnit` class.

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
