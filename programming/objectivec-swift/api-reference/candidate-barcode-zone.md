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

`DSCandidateBarcodeZone` class represents the information of a single candidate barcode zone. It records the location as well as the possible barcode formats of the barcode in the zone.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

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
| [`possibleFormats`](#possibleformats) | *DSBarcodeFormat* | The barcode format of the barcode. |

### location

The location of the candidate barcode zone.

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

The barcode format of the barcode.

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
