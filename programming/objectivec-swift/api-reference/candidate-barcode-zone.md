---
layout: default-layout
title: DSCandidateBarcodeZone Class - Dynamsoft Barcode Reader iOS Edition
description: DSCandidateBarcodeZone class of Dynamsoft Barcode Reader iOS edition represents the information of a single candidate barcode zone.
keywords: candidate barcode zone, DSCandidateBarcodeZone, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSCandidateBarcodeZone
---

# DSCandidateBarcodeZone Class

`DSCandidateBarcodeZone` is a class that represents the information of a single candidate barcode zone.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSCandidateBarcodeZone : NSObject
```
2. 
```swift
class CandidateBarcodeZone: NSObject
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`location`](#location) | *DSQuadrilateral* | The location of the candidate barcode zone. |
| [`possibleFormats`](#possibleformats) | *DSBarcodeFormat* | The possible barcode formats of the barcode in the candidate barcode zone. |

### location

The location of the candidate barcode zone within the image represented as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html).

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

### possibleFormats

The possible format(s) of the barcode in the candidate barcode zone as [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) items.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) DSBarcodeFormat possibleFormats;
```
2. 
```swift
var possibleFormats: DSBarcodeFormat { get set }
```
