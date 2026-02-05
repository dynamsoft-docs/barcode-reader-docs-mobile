---
layout: default-layout
title: DSECISegment Class - Dynamsoft Barcode Reader iOS Edition
description: DSECISegment class of Dynamsoft Barcode Reader iOS represents the Extended Channel Interpretation (ECI) information within a barcode, specifying the character encoding used for a portion of the decoded bytes.
keywords: DSECISegment, ECI, character encoding, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSECISegment
---

# DSECISegment Class

`DSECISegment` is a class that represents the Extended Channel Interpretation (ECI) information within a barcode. Each ECI segment specifies the character encoding used for a portion of the decoded bytes. The charset names follow the IANA character set registry (e.g. "UTF-8", "ISO-8859-1").

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSECISegment : NSObject
```
2. 
```swift
class ECISegment : NSObject
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`eciValue`](#ecivalue) | *NSInteger* | The ECI assignment number as defined by ISO/IEC 15424. |
| [`charsetEncoding`](#charsetencoding) | *NSString* | The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). |
| [`startIndex`](#startindex) | *NSInteger* | The start index of this ECI segment in the decoded barcode bytes. |
| [`length`](#length) | *NSInteger* | The length (in bytes) of this segment within the decoded barcode bytes. |

### eciValue

The ECI assignment number as defined by ISO/IEC 15424. This value identifies the character set encoding used in this segment.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger eciValue;
```
2. 
```swift
var eciValue: Int { get set }
```

### charsetEncoding

The charset encoding name defined by IANA (e.g. "UTF-8", "ISO-8859-1"). This specifies the character encoding scheme used to interpret the bytes in this segment.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) NSString *charsetEncoding;
```
2. 
```swift
var charsetEncoding: String? { get set }
```

### startIndex

The start index of this ECI segment in the decoded barcode bytes. This indicates the position where this segment begins within the overall decoded byte sequence.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger startIndex;
```
2. 
```swift
var startIndex: Int { get set }
```

### length

The length (in bytes) of this segment within the decoded barcode bytes. This specifies how many bytes in the decoded data belong to this ECI segment.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger length;
```
2. 
```swift
var length: Int { get set }
```
