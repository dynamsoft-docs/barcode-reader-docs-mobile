---
layout: default-layout
title: iOneDCodeDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iOneDCodeDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOneDCodeDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iOneDCodeDetails.html
---

# Class iOneDCodeDetails

`iOneDCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the OneD code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iOneDCodeDetails : NSObject
```
2. 
```swift
class iOneDCodeDetails : NSObject
```

| Attribute | Descriptions |
|---------- |------------- |
| [`moduleSize`](#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`startCharsBytes`](#startcharsbytes) | The start chars in a byte array. |
| [`stopCharsBytes`](#stopcharsbytes) | The stop chars in a byte array. |
| [`checkDigitBytes`](#checkdigitbytes) | The check digit chars in a byte array. |
| [`startPatternRange`](#startcharsbytes) | The position of the start pattern relative to the barcode location. |
| [`middlePatternRange`](#stopcharsbytes) | The position of the middle pattern relative to the barcode location. |
| [`endPatternRange`](#checkdigitbytes) | The position of the end pattern relative to the barcode location. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger moduleSize;
```
2. 
```swift
var moduleSize: Int { get set }
```

## startCharsBytes

The start chars in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* startCharsBytes;
```
2. 
```swift
var startCharsBytes: Data? { get set }
```

## stopCharsBytes

The stop chars in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* stopCharsBytes;
```
2. 
```swift
var stopCharsBytes: Data? { get set }
```

## checkDigitBytes

The check digit chars in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* checkDigitBytes;
```
2. 
```swift
var checkDigitBytes: Data? { get set }
```

## startPatternRange

The position of the start pattern relative to the barcode location.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSArray* startPatternRange;
```
2. 
```swift
var startPatternRange: [Any]? { get set }
```

## middlePatternRange

The position of the middle pattern relative to the barcode location

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSArray* middlePatternRange;
```
2. 
```swift
var middlePatternRange: [Any]? { get set }
```

## endPatternRange

The position of the end pattern relative to the barcode location.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) NSArray* endPatternRange;
```
2. 
```swift
var endPatternRange: [Any]? { get set }
```
