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

## Inheritance

DSLocalizedBarcodeElement inherits from DSRegionObjectElement.

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`possibleFormats`](#possibleformats) | *DSBarcodeFormat* |All possible formats of the localized barcode. |
| [`possibleFormatsString`](#possibleformatsstring) | *NSString \** |All possible formats of the localized barcode in one string. Splited by ",". |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the localized barcode zone. It represents the confidence that the positioning area is a barcode. |
| [`angle`](#angle) | *NSInteger* | The angle of the localized barcode zone. |
| [`moduleSize`](#modulesize) | *NSInteger* | The module size of the localized barcode. |

## Inherited Attributes

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`location`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#location) | *DSQuadrilateral \** | The location info of the element that defined in DSQuadrilateral. |
| [`referencedElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#referencedelement) | *DSRegionObjectElement \** | The referenced element that supports the capturing of this element. |
| [`regionObjectElementType`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#regionobjectelementtype) | *DSRegionObjectElementType* | The type of the element. |

### possibleFormats

All possible formats of the localized barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) DSBarcodeFormat possibleFormats;
```
2. 
```swift
var possibleFormats: DSBarcodeFormat { get }
```

### possibleFormatsString

All possible formats of the localized barcode in one string. Splited by ",".

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, copy, nullable, readonly) NSString *possibleFormatsString;
```
2. 
```swift
var possibleFormatsString: String? { get }
```

### confidence

The confidence of the localized barcode zone. It represents the confidence that the positioning area is a barcode.

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

### angle

The angle of the localized barcode zone.

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

The module size of the localized barcode.

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
