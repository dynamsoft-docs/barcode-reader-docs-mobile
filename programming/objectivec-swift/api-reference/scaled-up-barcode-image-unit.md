---
layout: default-layout
title: DSScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSScaledUpBarcodeImageUnit class represents a unit that contains scaled up barcode image. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSScaledUpBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/scaled-up-barcode-image-unit.html
---

# DSScaledUpBarcodeImageUnit Class

The `DSScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

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
| [`getImageData`](#getimagedata) | The up-scaled barcode image. |
| [`setImageData`](#setimagedata) | Set the up-scaled barcode image. |

## Inherited Methods

The following methods are inherited from class [`DSIntermediateResultUnit`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-ios.md -%}

### getImageData

Get the up-scaled barcode image.

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

**Return Value**

Returns a [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html) object as the up-scaled barcode image.

### setImageData

Set the up-scaled barcode image.

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

`[in] imageData`: A [`DSImageData`]({{ site.dcv_ios_api }}core/basic-structures/image-data.html) object as the up-scaled barcode image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
