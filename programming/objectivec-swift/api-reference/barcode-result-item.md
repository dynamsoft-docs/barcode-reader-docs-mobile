---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader iOS Edition
description: DSBarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from DSCapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, DSBarcodeResultItem, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeResultItem
permalink: /programming/objectivec-swift/api-reference/barcode-result-item.html
---

# DSBarcodeResultItem Class

The `DSBarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CCapturedResultItem`.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSBarcodeResultItem: DSCapturedResultItem
```
2. 
```swift
class BarcodeResultItem : DSCapturedResultItem
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`format`](#format) | *DSBarcodeFormat* | The format of the barcode. |
| [`formatString`](#formatstring) | *NSString \** | The format text of the barcode. |
| [`text`](#text) | *NSString \** | The decode text of the barcode. |
| [`bytes`](#bytes) | *NSData \** | The decode byte of the barcode. |
| [`location`](#location) | *DSQuadrilateral \** | The location of the barcode. It is defined by the vertex coordinates of the quadrilateral. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the decoding result. If the confidence is lower than 30, the result will not be output by default. |
| [`angle`](#angle) | *NSInteger* | The rotation angle of the barcode. |
| [`moduleSize`](#modulesize) | *NSInteger* | The module size of the barcode. |
| [`details`](#details) | *DSBarcodeDetails \** | The details of the decoded barcode. |
| [`isDPM`](#isdpm) | *BOOL* | Whether the barcode is a DPM barcode. |
| [`isMirrored`](#ismirrored) | *BOOL* | Whether the barcode is mirrored. |

### format

The format of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) DSBarcodeFormat format;
```
2. 
```swift
var format: DSBarcodeFormat { get }
```

### formatString

The format text of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSString *formatString;
```
2. 
```swift
var formatString: String? { get }
```

### text

The decode text of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSString *text;
```
2. 
```swift
var text: String? { get }
```

### bytes

The decode byte of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSData *bytes;
```
2. 
```swift
var bytes: Data? { get }
```

### location

The location of the barcode. It is defined by the vertex coordinates of the quadrilateral.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) DSQuadrilateral *location;
```
2. 
```swift
var location: DSQuadrilateral? { get }
```

### confidence

The confidence of the decoding result. If the confidence is lower than 30, the result will not be output by default.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) NSInteger confidence;
```
2. 
```swift
var confidence: Int { get }
```

### angle

The rotation angle of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) NSInteger angle;
```
2. 
```swift
var angle: Int { get }
```

### moduleSize

The module size of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) NSInteger moduleSize;
```
2. 
```swift
var moduleSize: Int { get }
```

### details

The details of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) DSBarcodeDetails *details;
```
2. 
```swift
var details: DSBarcodeDetails? { get }
```

### isDPM

Whether the barcode is a DPM barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) BOOL isDPM;
```
2. 
```swift
var isDPM: Bool { get }
```

### isMirrored

Whether the barcode is mirrored.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) BOOL isMirrored;
```
2. 
```swift
var isMirrored: Bool { get }
```
