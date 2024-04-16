---
layout: default-layout
title: DSLocalizedBarcodeElement Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodeElement class represents a localized barcode element detected in an image. It is inherited from DSRegionObjectElement class.
keywords: GetAngle, GetConfidence, GetFormat, GetFormatString, GetModuleSize, DSLocalizedBarcodeElement, api reference
permalink: /programming/objectivec-swift/api-reference/localized-barcode-element.html
---

# DSLocalizedBarcodeElement Class

The `DSLocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSLocalizedBarcodeElement : DSRegionObjectElement
```
2. 
```swift
class LocalizedBarcodeElement : RegionObjectElement
```

## Methods

| Methods | Description |
| ------- | ----------- |
| [`init`](#init) | Create a new `DSLocalizedBarcodeElement` object. |
| [`getAngle`](#getangle) | Get the angle of the localized barcode. |
| [`getConfidence`](#getconfidence) | Get the confidence of the localized barcode. |
| [`getPossibleFormats`](#getpossibleformats) | Get the possible formats of the localized barcode. |
| [`setPossibleFormat`](#setpossibleformat) | Set the possible format of the localized barcode. |
| [`getPossibleFormatsString`](#getpossibleformatsstring) | Get the possible formats of the localized barcode as a string. |
| [`getModuleSize`](#getmodulesize) | Get the module size of the localized barcode. |

## Inherited Methods

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

### init

Create a new `DSLocalizedBarcodeElement` object.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)init;
```
2. 
```swift
init()
```

### getAngle

Get the angle of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getAngle
```
2. 
```swift
func getAngle() -> NSInteger
```

**Return Value**

The angle of the localized barcode.

### getConfidence

Get the confidence of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getConfidence
```
2. 
```swift
func getConfidence() -> NSInteger
```

**Return Value**

The confidence of the localized barcode.

### getPossibleFormats

Get the possible formats of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSBarcodeFormat)getPossibleFormats
```
2. 
```swift
func getPossibleFormats() -> BarcodeFormat
```

**Return Value**

The possible formats of the localized barcode.

### setPossibleFormat

Set the possible format of the localized barcode. The possible format string is changed as well.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setPossibleFormat:(DSBarcodeFormat)possibleFormat
```
2. 
```swift
func setPossibleFormat(_ possibleFormat: BarcodeFormat) -> NSInteger
```

**Parameters**

`[in] possibleFormat`: The possible format of the localized barcode.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### getPossibleFormatsString

Get the possible formats of the localized barcode as a string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *)getPossibleFormatsString
```
2. 
```swift
func getPossibleFormatsString() -> String
```

**Return Value**

The possible formats of the localized barcode as a string.

### getModuleSize

Get the module size of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)getModuleSize
```
2. 
```swift
func getModuleSize() -> NSInteger
```

**Return Value**

The module size of the localized barcode.
