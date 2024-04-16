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

## Methods

| Methods | Description |
| ------- | ----------- |
| [`init`](#init) | Initialize a new `DSDecodedBarcodeElement` object. |
| [`getText`](#gettext) | Get the text of the decoded barcode. |
| [`setText`](#settext) | Set the text of the decoded barcode. |
| [`getBytes`](#getbytes) | Get the bytes of the decoded barcode. |
| [`setBytes`](#setbytes) | Set the bytes of the decoded barcode. |
| [`getFormat`](#getformat) | Get the format of the decoded barcode. |
| [`setFormat`](#setformat) | Set the format of the decoded barcode. |
| [`getConfidence`](#getconfidence) | Get the confidence of the decoded barcode. |
| [`setConfidence`](#setconfidence) | Set the confidence of the decoded barcode. |
| [`getFormatString`](#getformatstring) | Get the format string of the decoded barcode. |
| [`getAngle`](#getangle) | Get the angle of the decoded barcode. |
| [`getModuleSize`](#getmodulesize) | Get the module size of the decoded barcode. |
| [`getDetails`](#getdetails) | Get the details of the decoded barcode. |
| [`getExtendedBarcodeResults`](#getextendedbarcoderesults) | Get the extended barcode results of the decoded barcode. |
| [`isDPM`](#isdpm) | Check if the decoded barcode is DPM. |
| [`isMirrored`](#ismirrored) | Check if the decoded barcode is mirrored. |

## Inherited Attributes

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-ios.md -%}

### init

Create a new `DSDecodedBarcodeElement` object.

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

### getText

Get the text of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *)getText
```
2. 
```swift
func getText() -> String
```

**Return Value**

The text of the decoded barcode.

### setText

Set the text of the decoded barcode. The byte of the barcode is changed as well.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setText:(NSString *)text
```
2. 
```swift
func setText(text: String) -> NSInteger
```

**Parameters**

`[in] text`: The text of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### getBytes

Get the bytes of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSData *)getBytes
```
2. 
```swift
func getBytes() -> NSData
```

**Return Value**

The bytes of the decoded barcode.

### setBytes

Set the bytes of the decoded barcode. The text of the barcode is changed as well.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setBytes:(NSData *)bytes
```
2. 
```swift
func setBytes(bytes: NSData) -> NSInteger
```

**Parameters**

`[in] bytes`: The bytes of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### getFormat

Get the format of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSBarcodeFormat)getFormat
```
2. 
```swift
func getFormat() -> BarcodeFormat
```

**Return Value**

The format of the decoded barcode.

### setFormat

Set the format of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setFormat:(DSBarcodeFormat)format
```
2. 
```swift
func setFormat(_ format: BarcodeFormat) -> NSInteger
```

**Parameters**

`[in] format`: The format of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### getConfidence

Get the confidence of the decoded barcode.

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

The confidence of the decoded barcode.

### setConfidence

Set the confidence of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSInteger)setConfidence:(NSInteger)confidence
```
2. 
```swift
func setConfidence(_ confidence: NSInteger) -> NSInteger
```

**Parameters**

`[in] confidence`: The confidence of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### getFormatString

Get the format string of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (NSString *)getFormatString
```
2. 
```swift
func getFormatString() -> String
```

**Return Value**

The format string of the decoded barcode.

### getAngle

Get the angle of the decoded barcode.

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

The angle of the decoded barcode.

### getModuleSize

Get the module size of the decoded barcode.

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

The module size of the decoded barcode.

### getDetails

Get the details of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (DSBarcodeDetails *)getDetails
```
2. 
```swift
func getDetails() -> BarcodeDetails
```

**Return Value**

The details of the decoded barcode.

### getExtendedBarcodeResults

Get the extended barcode results of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (nullable NSArray<DSExtendedBarcodeResult *>*)getExtendedBarcodeResults
```
2. 
```swift
func getExtendedBarcodeResults() -> [ExtendedBarcodeResult]?
```

**Return Value**

The extended barcode results of the decoded barcode.

### isDPM

Check if the decoded barcode is DPM.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)isDPM
```
2. 
```swift
func isDPM() -> Bool
```

**Return Value**

Returns `true` if the decoded barcode is DPM. Otherwise, returns `false`.

### isMirrored

Check if the decoded barcode is mirrored.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (BOOL)isMirrored
```
2. 
```swift
func isMirrored() -> Bool
```

**Return Value**

Returns `true` if the decoded barcode is mirrored. Otherwise, returns `false`.
