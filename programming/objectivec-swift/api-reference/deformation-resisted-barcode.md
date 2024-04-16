---
layout: default-layout
title: DSDeformationResistedBarcode Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDeformationResistedBarcode class of Dynamsoft Barcode Reader iOS edition represents a deformation resisted barcode with its location, format and the image data.
keywords: image data, DSDeformationResistedBarcode, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDeformationResistedBarcode
permalink: /programming/objectivec-swift/api-reference/deformation-resisted-barcode.html
---

# DSDeformationResistedBarcode Class

The `DSDeformationResistedBarcode` class represents a deformation resisted barcode with its location, format and the image data.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDeformationResistedBarcode: NSobject
```
2. 
```swift
class DeformationResistedBarcode: NSobject
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`imageData`](#imagedata) | *DSImageData* | The deformation resisted barcode image data. |
| [`location`](#location) | *DSQuadrilateral* | The location of the deformation resisted barcode. |
| [`format`](#format) | *DSBarcodeFormat* | The barcode format of the deformation resisted barcode. |

### imageData

A `DSImageData` object as the deformation resisted barcode image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) DSImageData * imageData;
```
2. 
```swift
var imageData: DSImageData? { get set }
```

### location

A `DSQuadrilateral` object as the location of the deformation resisted barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, copy) DSQuadrilateral * location;
```
2. 
```swift
var location: DSQuadrilateral? { get set }
```

### format

A `DSBarcodeFormat` enum that represents the barcode format of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) DSBarcodeFormat format;
```
2. 
```swift
var format: DSBarcodeFormat { get set }
```
