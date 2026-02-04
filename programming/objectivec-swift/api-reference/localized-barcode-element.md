---
layout: default-layout
title: DSLocalizedBarcodeElement Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodeElement class of Dynamsoft Barcode Reader iOS represents a localized barcode element detected in an image. It is inherited from DSRegionObjectElement class.
keywords: GetAngle, GetConfidence, GetFormat, GetFormatString, GetModuleSize, DSLocalizedBarcodeElement, api reference
---

# DSLocalizedBarcodeElement Class

`DSLocalizedBarcodeElement` extends the [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html) class and represents a localized barcode element detected in an image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`init`](#init) | Creates a new `DSLocalizedBarcodeElement` object. |
| [`getAngle`](#getangle) | Returns the orientation angle of the localized barcode. |
| [`getConfidence`](#getconfidence) | Returns the confidence score of the localized barcode. |
| [`getPossibleFormats`](#getpossibleformats) | Returns the possible formats of the localized barcode. |
| [`setPossibleFormats`](#setpossibleformats) | Sets the possible formats of the localized barcode. |
| [`getPossibleFormatsString`](#getpossibleformatsstring) | Returns the possible formats of the localized barcode as a string. |
| [`getModuleSize`](#getmodulesize) | Returns the module size of the localized barcode. |
| [`setLocation`](#setlocation) | Sets the location of the localized barcode. |

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html).

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

Returns the orientation angle of the localized barcode element, indicating how the element is positioned or rotated within the barcode.

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

An integer representing the orientation angle of the localized barcode.

### getConfidence

Returns the confidence/reliability score of the localization of the barcode element.

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

An integer representing the confidence score of the localized barcode element, which represents the confidence that the positioning area is a barcode.

### getPossibleFormats

Returns the possible formats of the localized barcode since the barcode has not been decoded yet, so the exact format is not yet determined.

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

The possible format(s) of the localized barcode as [DSBarcodeFormat]({{ site.dcvb_ios_api }}core/enum//barcode-format.html?lang=objc,swift) enumeration item(s).


### setPossibleFormats

Set the possible format of the localized barcode. The possible format string is changed as well.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setPossibleFormats:(DSBarcodeFormat)possibleFormats;
```
2. 
```swift
func setPossibleFormats(_ possibleFormats: BarcodeFormat)
```

**Parameters**

`[in] possibleFormats`: The possible [DSBarcodeFormat]({{ site.dcvb_ios_api }}core/enum//barcode-format.html?lang=objc,swift) of the localized barcode.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### getPossibleFormatsString

Returns the possible format(s) of the localized barcode as a string, with each format split by a comma (","). Since the barcode has not been decoded yet, the exact format is not yet determined.

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

A string representing all the possible formats of the localized barcode.

### getModuleSize

Returns the size of the individual modules within the localized barcode element.

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

An integer representing the module size of the localized barcode.

### setLocation

Sets the location of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setLocation:(DSQuadrilateral *)location;
```
2. 
```swift
func setLocation(_ location: DSQuadrilateral)
```

**Parameters**

`location`: The location of the localized barcode as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html) object.

**Return Value**

Returns 0 if the location is set successfully, otherwise returns the error code.
