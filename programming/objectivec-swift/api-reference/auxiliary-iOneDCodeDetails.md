---
layout: default-layout
title: DSOneDCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: The DSOneDCodeDetails class of Dynamsoft Barcode Reader iOS represents a barcode in OneD format. It inherits from the DSBarcodeDetails class and contains information about the start & stop char bytes, check digit bytes, and pattern ranges of the barcode.
keywords: DSOneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSOneDCodeDetails
---

# DSOneDCodeDetails

`DSOneDCodeDetails` extends the [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information specific to a 1D (one dimensional) barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`startCharsBytes`](#startcharsbytes) | *NSData \** | The start characters of the 1D barcode in a byte array. |
| [`stopCharsBytes`](#stopcharsbytes) | *NSData \** | The stop characters of the 1D barcode in a byte array. |
| [`checkDigitBytes`](#checkdigitbytes) | *NSData \** | The check digit characters of the 1D barcode in a byte array. |
| [`startPatternRange`](#startpatternrange) | *UIFloatRange* | The position range of the start pattern relative to the barcode's location. |
| [`middlePatternRange`](#middlepatternrange) | *UIFloatRange* | The position range of the middle pattern relative to the barcode's location. |
| [`endPatternRange`](#endpatternrange) | *UIFloatRange* | The position range of the end pattern relative to the barcode's location. |

### startCharsBytes

A [NSData](https://developer.apple.com/documentation/foundation/nsdata){:target="_blank"} object representing the start characters of the 1D barcode in a byte array. Start characters are often used to identify the beginning of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly, copy, nullable) NSData *startCharsBytes;
```
2. 
```swift
var startCharsBytes: Data? { get }
```

### stopCharsBytes


A [NSData](https://developer.apple.com/documentation/foundation/nsdata){:target="_blank"} object representing the stop characters of the 1D barcode in a byte array. Stop characters are often used to identify the end of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly, copy, nullable) NSData *stopCharsBytes;
```
2. 
```swift
var stopCharsBytes: Data? { get }
```

### checkDigitBytes

A [NSData](https://developer.apple.com/documentation/foundation/nsdata){:target="_blank"} object representing the check digit characters of the 1D barcode in a byte array. Check digits are used for error detection and correction in some 1D barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly, copy, nullable) NSData *checkDigitBytes;
```
2. 
```swift
var checkDigitBytes: Data? { get }
```

### startPatternRange

A [UIFloatRange](https://developer.apple.com/documentation/uikit/uifloatrange){:target="_blank"} representing the position range of the start pattern relative to the barcode's location.

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

A [UIFloatRange](https://developer.apple.com/documentation/uikit/uifloatrange){:target="_blank"} representing the position range of the middle pattern relative to the barcode's location.

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

A [UIFloatRange](https://developer.apple.com/documentation/uikit/uifloatrange){:target="_blank"} representing the position range of the end pattern relative to the barcode's location.

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
