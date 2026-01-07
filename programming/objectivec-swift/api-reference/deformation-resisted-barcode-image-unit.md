---
layout: default-layout
title: DSDeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDeformationResistedBarcodeImageUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains deformation resisted barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSDeformationResistedBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDeformationResistedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/deformation-resisted-barcode-image-unit.html
---

# DSDeformationResistedBarcodeImageUnit Class

`DSDeformationResistedBarcodeImageUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the deformation-resisted barcode, including corresponding image data, its location, and the barcode format.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getDeformationResistedBarcode`](#getdeformationresistedbarcode) | Returns the deformation-resisted barcode. |
| [`setDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation-resisted barcode onto the original image |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getDeformationResistedBarcode

Returns the deformation-resisted barcode as a [`DSDeformationResistedBarcode`](deformation-resisted-barcode.md) object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(DSDeformationResistedBarcode *)getDeformationResistedBarcode;
```
2. 
```swift
func getDeformationResistedBarcode() -> DeformationResistedBarcode
```

**Return Value**

A [`DSDeformationResistedBarcode`](deformation-resisted-barcode.md) object representing the deformation-resisted barcode.

### setDeformationResistedBarcode

Sets the deformation-resisted barcode onto the original image using a transformation matrix.

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

**Parameters**

`[in] barcode`: A [`DeformationResistedBarcode`](deformation-resisted-barcode.md) object as the deformation-resisted barcode.

`[in] matrixToOriginalImage`: A `CGAffineTransform` object as the transformation matrix to the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
