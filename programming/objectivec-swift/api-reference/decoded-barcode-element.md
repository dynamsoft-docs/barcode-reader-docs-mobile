---
layout: default-layout
title: DSDecodedBarcodeElement Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodeElement class of Dynamsoft Barcode Reader iOS represents a decoded barcode element. It inherits from the DSRegionObjectElement class and provides additional functionality for retrieving information about the decoded barcode.
keywords: text, bytes, DSDecodedBarcodeElement, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodeElement
---

# DSDecodedBarcodeElement Class

`DSDecodedBarcodeElement` extends the [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html) class and represents a decoded barcode element.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`getText`](#gettext) | Returns the text of the decoded barcode. |
| [`setText`](#settext) | Set the text of the decoded barcode. |
| [`getBytes`](#getbytes) | Returns the raw bytes of the decoded barcode. |
| [`setBytes`](#setbytes) | Set the raw bytes of the decoded barcode. |
| [`getFormat`](#getformat) | Returns the format of the decoded barcode. |
| [`setFormat`](#setformat) | Set the format of the decoded barcode. |
| [`getConfidence`](#getconfidence) | Returns the confidence score of the decoded barcode. |
| [`setConfidence`](#setconfidence) | Set the confidence of the decoded barcode. |
| [`getFormatString`](#getformatstring) | Returns the format string of the decoded barcode. |
| [`getAngle`](#getangle) | Returns the orientation angle of the decoded barcode. |
| [`getModuleSize`](#getmodulesize) | Returns the module size of the decoded barcode. |
| [`getDetails`](#getdetails) | Returns the `DSBarcodeDetails` of the decoded barcode. |
| [`getExtendedBarcodeResults`](#getextendedbarcoderesults) | Returns the extended barcode results of the decoded barcode. |
| [`isDPM`](#isdpm) | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](#ismirrored) | Specifies if the decoded barcode is mirrored or not. |
| [`setLocation`](#setlocation) | Sets the location of the decoded barcode. |

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html).

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

Returns the text of the decoded barcode.

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

A string representing the text of the decoded barcode.

### setText

Set the text of the decoded barcode. The barcode bytes are changed as well to reflect the new text.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setText:(NSString *)text
```
2. 
```swift
func setText(text: String)
```

**Parameters**

`[in] text`: The text to be set for the decoded barcode.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### getBytes

Returns the raw bytes of the decoded barcode.

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

A [NSData](https://developer.apple.com/documentation/foundation/nsdata){:target="_blank"} object representing the raw bytes of the decoded barcode.

### setBytes

Set the raw bytes of the decoded barcode. The text of the barcode will change to reflect the new barcode bytes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setBytes:(NSData *)bytes
```
2. 
```swift
func setBytes(bytes: NSData)
```

**Parameters**

`[in] bytes`: The bytes of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### getFormat

Returns the format of the decoded barcode as a [`DSBarcodeFormat`]({{site.dcvb_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) item.

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

A [`DSBarcodeFormat`]({{site.dcvb_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) item representing the format of the decoded barcode.

### setFormat

Set the format of the decoded barcode using a [`DSBarcodeFormat`]({{site.dcvb_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) item.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setFormat:(DSBarcodeFormat)format
```
2. 
```swift
func setFormat(_ format: BarcodeFormat)
```

**Parameters**

`[in] format`: The format of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### getConfidence

Returns the confidence score of the decoded barcode.

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

An integer representing the confidence score.

### setConfidence

Set the confidence score of the decoded barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)setConfidence:(NSInteger)confidence
```
2. 
```swift
func setConfidence(_ confidence: NSInteger)
```

**Parameters**

`[in] confidence`: The confidence of the decoded barcode.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### getFormatString

Returns the format of the decode barcode as a string.

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

A string representing the format of the barcode.

### getAngle

Returns the orientation angle of the decoded barcode should it be rotated in any way.

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

An integer representing the orientation angle of the barcode.

### getModuleSize

Returns the module size of the decoded barcode.

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

An integer representing the module size of the decoded barcode.

### getDetails

Returns the [`BarcodeDetails`](barcode-details.md) of the decoded barcode.

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

A [`DSBarcodeDetails`](barcode-details.md) object representing the details of the decoded barcode.

### getExtendedBarcodeResults

Returns the extended barcode result(s) of the decoded barcode as a [`DSExtendedBarcodeResult`](auxiliary-iExtendedResult.md) object. Please visit the `DSExtendedBarcodeResult` page to learn more of what information is contained there.

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

An array of [`DSExtendedBarcodeResult`](auxiliary-iExtendedResult.md) that represents the extended barcode results.

### isDPM

Specifies if the decoded barcode is a Direct Part Marking (DPM) code or not. DPM codes are read by setting the [`DPMCodeReadingModes`]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/dpm-code-reading-modes.html).

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

A `BOOL` value describing whether the barcode is a DPM code or not.

### isMirrored

Specifies if the decoded barcode is mirrored or not. Mirrored barcodes are read by setting the [`MirrorMode`]({{site.dcvb_parameters_reference}}barcode-format-specification/mirror-mode.html).

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

A `BOOL` value describing whether the barcode is mirrored or not.

### setLocation

Sets the location of the decoded barcode.

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

`[in] location`: The location of the decoded barcode as a [`DSQuadrilateral`]({{ site.dcvb_ios_api }}core/basic-structures/quadrilateral.html) object.

**Return Value**

Returns 0 if the location is set successfully, otherwise returns the error code.
