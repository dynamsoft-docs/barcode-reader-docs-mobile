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

`DSBarcodeResultItem` extends the [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html) class and represents a single barcode result. This is the most basic item of the decoded barcode result, one of the captured result types that the Capture Vision Router can output.

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
| [`location`](#location) | *DSQuadrilateral \** | The location of the barcode. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the decoding result. |
| [`angle`](#angle) | *NSInteger* | The rotation angle of the barcode. |
| [`moduleSize`](#modulesize) | *NSInteger* | The module size of the barcode. |
| [`details`](#details) | *DSBarcodeDetails \** | The details of the decoded barcode. |
| [`isDPM`](#isdpm) | *BOOL* | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](#ismirrored) | *BOOL* | Specifies if the decoded barcode is mirrored or not. |

The following attributes are inherited from [`DSCapturedResultItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`type`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#type) | *DSCapturedResultItemType* | The type of the captured result item. |
| [`referencedItem`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#referenceditem) | *DSCapturedResultItem \** | The referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |
| [`targetROIDefName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#targetroidefname) | *NSString* | The name of the [`TargetROIDef`]({{ site.dcv_parameters_reference }}target-roi-def/){:target="_blank"} object which includes a task that generated the result. |
| [`taskName`]({{ site.dcv_ios_api }}core/basic-structures/captured-result-item.html#taskname) | *NSString* | The name of the task that generated the result. |

### format

The format of the barcode. This format will be one of the [`DSBarcodeFormat`]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) enumerations.

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

The format of the barcode, but as a string instead of a `DSBarcodeFormat` enumeration item. 

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

The raw bytes of the decoded barcode text which is useful when the text string cannot be used.

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

The location of the barcode as a [`DSQuadrilateral`]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html). The quadrilateral contains the four vertices of the location, with the first vertex in the `points` array being the top-left most vertex, and then going in a clockwise direction.

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

The confidence of the decoded result, which is a measure of the result's accuracy or reliability. If the confidence is lower than 30, the result will not be output by default. To change the minimum accepted confidence score for a barcode, please see the [`minResultConfidence`](simplified-barcode-reader-settings.md#minresultconfidence) setting.

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

If the barcode is captured at an angle or is rotated by any measure, this property represents the rotation angle of the barcode.

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

The size of the individual modules or elements within the barcode.

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

The details of the decoded barcode. [DSBarcodeDetails](barcode-details.md) can offer much more enhanced details specific to the barcode format of the decoded barcode. If you would like to learn more about how you can use these barcode details, please see this article on [how to get detailed barcode info]({{site.features}}get-detailed-info.html?lang=objc,swift).

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

Specifies if the decoded barcode is a Direct Part Marking (DPM) code or not. To learn how to read DPM codes, please visit [how to read DPM codes]({{site.usecases}}read-dpm-codes.html?lang=objc,swift).

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

Specifies if the decoded barcode is mirrored or not. Mirrored barcodes are read by setting the [`MirrorMode`]({{site.dcv_parameters_reference}}barcode-format-specification/mirror-mode.html){:target="_blank"}.

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
