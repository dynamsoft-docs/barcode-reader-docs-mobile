---
layout: default-layout
title: DSComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSComplementedBarcodeImageUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains complemented barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSComplementedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/complemented-barcode-image-unit.html
---

# DSComplementedBarcodeImageUnit Class

`DSComplementedBarcodeImageUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the complemented barcode image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getImageData`](#getimagedata) | Returns the `DSImageData` of the complemented barcode. |
| [`getLocation`](#getlocation) | Returns the location of the complemented barcode. |
| [`setLocation`](#setlocation) | Sets the location of the complemented barcode. |

The following methods are inherited from the class [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getImageData

Returns the [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) of the complemented barcode.

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

A [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) object.

### getLocation

Returns the location of the complemented barcode as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html).

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

A [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html) object representing the location.

### setLocation

Sets the location of the complemented barcode within the original image.

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

`location`: The location of the complemented barcode as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html) object.

`matrixToOriginalImage`: The `CGAffineTransform` matrix of the  original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
