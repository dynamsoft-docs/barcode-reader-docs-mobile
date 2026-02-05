---
layout: default-layout
title: DSDeformationResistedBarcode Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDeformationResistedBarcode class of Dynamsoft Barcode Reader iOS edition represents a deformation resisted barcode with its location, format and the image data.
keywords: image data, DSDeformationResistedBarcode, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDeformationResistedBarcode
---

# DSDeformationResistedBarcode Class

`DSDeformationResistedBarcode` is a class that represents a deformation-resisted barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`imageData`](#imagedata) | *DSImageData* | The deformation-resisted barcode image data. |
| [`location`](#location) | *DSQuadrilateral* | The location of the deformation-resisted barcode. |
| [`format`](#format) | *DSBarcodeFormat* | The barcode format of the deformation-resisted barcode. |

### imageData

A [`DSImageData`]({{ site.dcvb_ios_api }}core/basic-structures/image-data.html) object representing the deformation-resisted barcode image.

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

The location of the deformation-resisted barcode within the image represented as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSQuadrilateral * location;
```
2. 
```swift
var location: DSQuadrilateral? { get set }
```

### format

A [`DSBarcodeFormat`]({{site.dcvb_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) enum that represents the format of the deformation-resisted barcode.

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
