---
layout: default-layout
title: DSExtendedBarcodeResult Class - Dynamsoft Barcode Reader iOS Edition
description: DSExtendedBarcodeResult class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: DSExtendedBarcodeResult, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSExtendedBarcodeResult
permalink: /programming/objectivec-swift/api-reference/auxiliary-ExtendedResult.html
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
