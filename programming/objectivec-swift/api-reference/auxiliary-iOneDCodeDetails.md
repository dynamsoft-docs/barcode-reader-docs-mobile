---
layout: default-layout
title: DSOneDCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: The DSOneDCodeDetails class represents a barcode in OneD format. It inherits from the DSBarcodeDetails class and contains information about the start & stop char bytes, check digit bytes, and pattern ranges of the barcode.
keywords: DSOneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSOneDCodeDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-OneDCodeDetails.html
---

# DSOneDCodeDetails

The `DSOneDCodeDetails` class represents a barcode in OneD format. It inherits from the `DSBarcodeDetails` class and contains information about the char bytes, digit bytes, and pattern range.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSOneDCodeDetails : DSBarcodeDetails
```
2. 
```swift
class OneDCodeDetails : BarcodeDetails
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`startCharsBytes`](#startcharsbytes) | *NSData \** | The start chars of the one-dimensional barcode in a byte array. |
| [`stopCharsBytes`](#stopcharsbytes) | *NSData \** | The stop chars of the one-dimensional barcode in a byte array. |
| [`checkDigitBytes`](#checkdigitbytes) | *NSData \** | The check digit chars of the one-dimensional barcode in a byte array. |
| [`startPatternRange`](#startpatternrange) | *UIFloatRange* | The position of the start pattern relative to the barcode location. |
| [`middlePatternRange`](#middlepatternrange) | *UIFloatRange* | The position of the middle pattern relative to the barcode location. |
| [`endPatternRange`](#endpatternrange) | *UIFloatRange* | The position of the end pattern relative to the barcode location. |

### startCharsBytes

The start chars of the one-dimensional barcode in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSData *startCharsBytes;
```
2. 
```swift
var startCharsBytes: Data? { get }
```

### stopCharsBytes

The stop chars of the one-dimensional barcode in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSData *stopCharsBytes;
```
2. 
```swift
var stopCharsBytes: Data? { get }
```

### checkDigitBytes

The check digit chars of the one-dimensional barcode in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSData *checkDigitBytes;
```
2. 
```swift
var checkDigitBytes: Data? { get }
```

### startPatternRange

The position of the start pattern relative to the barcode location.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) UIFloatRange startPatternRange;
```
2. 
```swift
var startPatternRange: UIFloatRange { get }
```

### middlePatternRange

The position of the middle pattern relative to the barcode location.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) UIFloatRange middlePatternRange;
```
2. 
```swift
var middlePatternRange: UIFloatRange { get }
```

### endPatternRange

The position of the end pattern relative to the barcode location.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) UIFloatRange endPatternRange;
```
2. 
```swift
var endPatternRange: UIFloatRange { get }
```
