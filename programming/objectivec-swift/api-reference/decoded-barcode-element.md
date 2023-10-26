---
layout: default-layout
title: DSDecodedBarcodeElement Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodeElement class represents a decoded barcode element. It inherits from the DSRegionObjectElement class and provides additional functionality for retrieving information about the decoded barcode.
keywords: text, bytes, DSDecodedBarcodeElement, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodeElement
permalink: /programming/objectivec-swift/api-reference/decoded-barcode-element.html
---

# DSDecodedBarcodeElement Class

The `DSDecodedBarcodeElement` class represents a decoded barcode element. It inherits from the [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html) class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDecodedBarcodeElement: DSRegionObjectElement
```
2. 
```swift
class DecodedBarcodeElement: RegionObjectElement
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`text`](#text) | *NSString \** | The text of the decoded barcode. |
| [`bytes`](#bytes) | *NSData \** | The raw bytes of the decoded barcode. |
| [`isDPM`](#isdpm) | *BOOL* |Whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode). |
| [`isMirrored`](#ismirrored) | *BOOL* |Whether the barcode is mirrored (decoded by MirrorMode). |
| [`format`](#format) | *DSBarcodeFormat* |The format of the decoded barcode as a barcode format enumeration. |
| [`formatString`](#formatstring) | *NSString \** | The format of the decode barcode as a string. |
| [`angle`](#angle) | *NSInteger* |The orientation angle of the barcode. |
| [`moduleSize`](#modulesize) | *NSInteger* |The module size of the decoded barcode. |
| [`confidence`](#confidence) | *NSInteger* |The confidence score of the barcode recognition result. |
| [`details`](#details) | *DSBarcodeDetails \** | The details of the decoded barcode. |
| [`extendedBarcodeResults`](#extendedbarcoderesults) | *NSArray<DSExtendedBarcodeResult *> \** |An array of extended barcode results. |

## Inherited Attributes

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`location`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#location) | *DSQuadrilateral \** | The location info of the element that defined in DSQuadrilateral. |
| [`referencedElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#referencedelement) | *DSRegionObjectElement \** | The referenced element that supports the capturing of this element. |
| [`regionObjectElementType`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#regionobjectelementtype) | *DSRegionObjectElementType* | The type of the element. |

### text

The text of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSString* text;
```
2. 
```swift
var text: String? { get }
```

### bytes

The raw bytes of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSData* bytes;
```
2. 
```swift
var bytes: Data? { get }
```

### isDPM

Whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) BOOL isDPM;
```
2. 
```swift
var isDPM: Bool { get }
```

### isMirrored

Whether the barcode is mirrored (decoded by MirrorMode).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) BOOL isMirrored;
```
2. 
```swift
var isMirrored: Bool { get }
```

### format

The format of the decoded barcode as a barcode format enumeration.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) DSBarcodeFormat format;
```
2. 
```swift
var format: DSBarcodeFormat { get }
```

### formatString

The format of the decode barcode as a string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSString * formatString;
```
2. 
```swift
var formatString: String { get }
```

### angle

The orientation angle of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger angle;
```
2. 
```swift
var angle: Int { get }
```

### moduleSize

The module size of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger moduleSize;
```
2. 
```swift
var moduleSize: Int { get }
```

### confidence

The confidence score of the barcode recognition result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger confidence;
```
2. 
```swift
var confidence: Int { get }
```

### details

The details of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) DSBarcodeDetails* details;
```
2. 
```swift
var details: DSBarcodeDetails? { get }
```

### extendedBarcodeResults

An array of extended barcode results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSArray<DSExtendedBarcodeResult *>* extendedBarcodeResults;
```
2. 
```swift
var extendedBarcodeResults: [DSExtendedBarcodeResult]? { get }
```
