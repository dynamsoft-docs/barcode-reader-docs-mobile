---
layout: default-layout
title: DSScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSScaledUpBarcodeImageUnit class of Dynamsoft Barcode Reader iOS represents a unit that contains scaled up barcode image. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSScaledUpBarcodeImageUnit
---

# DSScaledUpBarcodeImageUnit Class

`DSScaledUpBarcodeImageUnit` extends the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) that represents a unit which contains a scaled-up barcode image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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

## Methods

| Methods | Description |
| ------- | ----------- |
| [`getImageData`](#getimagedata) | Returns the `DSImageData` of the scaled-up barcode image |
| [`setImageData`](#setimagedata) | Sets the scaled-up barcode image of the unit. |

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getImageData

Returns the [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) of the scaled-up barcode image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(nullable DSImageData *)getImageData;
```
2. 
```swift
func getImageData() -> DSImageData?
```

**Return value**

A `DSImageData` object representing the scaled-up barcode image.

### setImageData

Sets the scaled-up barcode image of the unit.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
-(NSInteger)setImageData:(DSImageData *)imageData;
```
2. 
```swift
func setImageData(_ imageData: DSImageData) -> Int
```

**Parameters**

`[in] imageData`: A [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) object as the scaled-up barcode image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
