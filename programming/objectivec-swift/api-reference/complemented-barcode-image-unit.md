---
layout: default-layout
title: DSComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSComplementedBarcodeImageUnit class represents a unit that contains complemented barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSComplementedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/complemented-barcode-image-unit.html
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

## Methods

| Method | Description |
|------- |-------------|
| [`getImageData`](#getimagedata) | Gets the complemented barcode image data. |
| [`setImageData`](#setimagedata) | Sets the complemented barcode image data. |
| [`getLocation`](#getlocation) | Gets the location. |
| [`setLocation`](#setlocation) | Sets the location. |

## Inherited Methods

The following methods are inherited from the class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getImageData

Gets the complemented barcode image data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable DSImageData *)getImageData
```
2. 
```swift
func getImageData() -> DSImageData?
```

**Return Value**

A `DSImageData` as the complemented barcode image data.

### getLocation

Gets the location of the complemented barcode image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSQuadrilateral *)getLocation
```
2. 
```swift
func getLocation() -> DSQuadrilateral
```

**Return Value**

A `DSQuadrilateral` as the location of the complemented barcode image.

### setLocation

Sets the location of the complemented barcode image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setLocation:(DSQuadrilateral *)location
   matrixToOriginalImage:(CGAffineTransform)matrixToOriginalImage
```
2. 
```swift
func setLocation(location: DSQuadrilateral, matrixToOriginalImage: CGAffineTransform) -> Int
```

**Parameters**

`location`: The location of the complemented barcode image.

`matrixToOriginalImage`: The matrix to original image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
