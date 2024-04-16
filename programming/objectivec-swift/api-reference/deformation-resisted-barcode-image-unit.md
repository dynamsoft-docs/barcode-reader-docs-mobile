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

## Methods

| Method | Description |
|------- |-------------|
| [`getDeformationResistedBarcode`](#getdeformationresistedbarcode) | Gets the deformation resisted barcode. |
| [`setDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation resisted barcode. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getDeformationResistedBarcode

Gets the deformation resisted barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(DSDeformationResistedBarcode *)getDeformationResistedBarcode
```
2. 
```swift
func getDeformationResistedBarcode() -> DeformationResistedBarcode
```

**Return Value**

The deformation resisted barcode.

### setDeformationResistedBarcode

Sets the deformation resisted barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setDeformationResistedBarcode:(DSDeformationResistedBarcode*)barcode
                    matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage
```
2. 
```swift
func setDeformationResistedBarcode(barcode: DeformationResistedBarcode, matrixToOriginalImage: CGAffineTransform) -> Int
```
