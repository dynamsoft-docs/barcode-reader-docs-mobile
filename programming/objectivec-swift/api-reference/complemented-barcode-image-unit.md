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

The `DSComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `DSIntermediateResultUnit` class.

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
