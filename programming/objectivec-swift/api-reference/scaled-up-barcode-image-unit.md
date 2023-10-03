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

The `DSScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `DSIntermediateResultUnit` class.

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

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData \** | The up-scaled barcode image. |

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
