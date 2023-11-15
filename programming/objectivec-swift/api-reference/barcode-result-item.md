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

The `DSBarcodeResultItem` class represents a barcode result item decoded by barcode reader. It is derived from [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html).

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

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

## Inherited Attributes

The following attributes are inherited from class [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`type`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#type) | *DSCapturedResultItemType* | The type of the captured result item. |
| [`referencedItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#referenceditem) | *DSCapturedResultItem \** | The referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |

### format

Returns the format of the barcode. This format will be one of the [DSBarcodeFormat]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) enumerations.

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

Returns the format of the barcode, but as text instead of a `DSBarcodeFormat` item. 

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

The raw decoded text of the barcode.

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

Returns the raw bytes of the decoded barcode text.

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

Returns the location of the barcode as a [DSQuadrilateral]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html). The quadrilateral contains the four vertex points of the location, with the first vertex being the left-most vertex, and going in a clockwise direction.

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

Returns the confidence of the decoded result, which is a measure of the result's accuracy. If the confidence is lower than 30, the result will not be output by default.

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

If the barcode is captured at an angle, this property returns the rotation angle of the barcode.

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

Returns the module size of the barcode.

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

Returns the details of the decoded barcode. [DSBarcodeDetails](barcode-details.md) can offer much more enhanced details specific to the barcode format of the decoded barcode. If you would like to learn more about how you can use these barcode details, please see this article on [how to get detailed barcode info]({{site.features}}get-detailed-info.html?lang=objc,swift).

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

Tells you whether the barcode is a DPM barcode, which is a unique type of Datamatrix code.

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

Returns whether the barcode is mirrored.

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
