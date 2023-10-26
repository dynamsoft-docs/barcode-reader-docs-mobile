---
layout: default-layout
title: DSExtendedBarcodeResult Class - Dynamsoft Barcode Reader iOS Edition
description: DSExtendedBarcodeResult class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: DSExtendedBarcodeResult, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSExtendedBarcodeResult
permalink: /programming/objectivec-swift/api-reference/auxiliary-iExtendedResult.html
---


# DSExtendedBarcodeResult

The `DSExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSExtendedBarcodeResult: DSDecodedBarcodeElement
```
2. 
```swift
class ExtendedBarcodeResult: DecodedBarcodeElement
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`extendedBarcodeResultType`](#extendedbarcoderesulttype) | *DSExtendedBarcodeResultType* | Get the type of the extended barcode result. |
| [`deformation`](#deformation) | *NSInteger* | Get the deformation level of the barcode zone. |
| [`clarity`](#clarity) | *NSInteger* | Get the clarity level of the barcode zone. |
| [`samplingImage`](#samplingimage) | *DSImageData \** | Get the sampling image of the barcode zone. |

## Inherited Attributes

The following attributes are inherited from class [`DecodedBarcodeElement`](decoded-barcode-element.md).

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`text`](decoded-barcode-element.md#text) | *NSString \** | The text of the decoded barcode. |
| [`bytes`](decoded-barcode-element.md#bytes) | *NSData \** | The raw bytes of the decoded barcode. |
| [`isDPM`](decoded-barcode-element.md#isdpm) | *BOOL* |Whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode). |
| [`isMirrored`](decoded-barcode-element.md#ismirrored) | *BOOL* |Whether the barcode is mirrored (decoded by MirrorMode). |
| [`format`](decoded-barcode-element.md#format) | *DSBarcodeFormat* |The format of the decoded barcode as a barcode format enumeration. |
| [`formatString`](decoded-barcode-element.md#formatstring) | *NSString \** | The format of the decode barcode as a string. |
| [`angle`](decoded-barcode-element.md#angle) | *NSInteger* |The orientation angle of the barcode. |
| [`moduleSize`](decoded-barcode-element.md#modulesize) | *NSInteger* |The module size of the decoded barcode. |
| [`confidence`](decoded-barcode-element.md#confidence) | *NSInteger* |The confidence score of the barcode recognition result. |
| [`details`](decoded-barcode-element.md#details) | *DSBarcodeDetails \** | The details of the decoded barcode. |
| [`extendedBarcodeResults`](decoded-barcode-element.md#extendedbarcoderesults) | *NSArray<DSExtendedBarcodeResult *> \** |An array of extended barcode results. |

The following attributes are inherited from class [`DSRegionObjectElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html).

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`location`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#location) | *DSQuadrilateral \** | The location info of the element that defined in DSQuadrilateral. |
| [`referencedElement`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#referencedelement) | *DSRegionObjectElement \** | The referenced element that supports the capturing of this element. |
| [`regionObjectElementType`]({{ site.dcv_ios_api }}core/intermediate-results/region-object-element.html#regionobjectelementtype) | *DSRegionObjectElementType* | The type of the element. |

### extendedBarcodeResultType

Get the type of the extended barcode result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) DSExtendedBarcodeResultType extendedBarcodeResultType;
```
2. 
```swift
var extendedBarcodeResultType: ExtendedBarcodeResultType { get }
```

### deformation

Get the deformation level of the barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger deformation;
```
2. 
```swift
var deformation: Int { get }
```

### clarity

Get the clarity level of the barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger clarity;
```
2. 
```swift
var clarity: Int { get }
```

### samplingImage

Get the sampling image of the barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) DSImageData *samplingImage;
```
2. 
```swift
var samplingImage: ImageData? { get }
```
