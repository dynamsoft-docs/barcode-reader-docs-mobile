---
layout: default-layout
title: DSDecodedBarcodesResult Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DSDecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesResult
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-result.html
---

# DSDecodedBarcodesResult Class

`DSDecodedBarcodesResult` represents a collection of [`DSBarcodeResultItem`](barcode-result-item.md), the basic unit of a decoded barcode result. It provides access to information about the decoded barcodes of an image/frame, the source image/frame, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDecodedBarcodesResult : NSObject
```
2. 
```swift
class DecodedBarcodesResult : NSObject
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`items`](#items) | *NSArray<DSBarcodeResultItem\*> \** | An array of `DSBarcodeResultItem`, which is the basic unit of the captured results. |
| [`originalImageTag`](#originalimagetag) | *DSImageTag \** | The `ImageTag` of the original image. |
| [`originalImageHashId`](#originalimagehashid) | *NSString \** | The hash ID of the original image. |
| [`rotationTransformMatrix`](#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`](#errorcode) | *NSInteger* | The error code should something go wrong during the barcode recognition process. |
| [`errorMessage`](#errormessage) | *NSString \** | The error message associated with the error code should something go wrong during the barcode recognition process. |

## items

An array of [`DSBarcodeResultItem`](barcode-result-item.md), which is the basic unit of the barcode capture results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, readonly) NSArray<DSBarcodeResultItem *> *items;
```
2. 
```swift
var items: [DSBarcodeResultItem]? { get }
```

## originalImageHashId

The hash ID of the original image. You can use this ID to get the original image via [`DSIntermediateResultManager`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html) class.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, copy, readonly) NSString *originalImageHashId;
```
2. 
```swift
var originalImageHashId: String? { get }
```

## originalImageTag

The [`ImageTag`]({{ site.dcvb_ios_api }}core/basic-structures/image-tag.html) of the source image. The image tag contains info about the image such as the image ID and the image capture distance mode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, readonly) DSImageTag *originalImageTag;
```
2. 
```swift
var originalImageTag: DSImageTag? { get }
```

## rotationTransformMatrix

The rotation transformation matrix of the original image relative to the rotated image. Please see [CGAffineTransform](https://developer.apple.com/documentation/corefoundation/cgaffinetransform){:target="_blank"} for more info.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) CGAffineTransform rotationTransformMatrix;
```
2. 
```swift
var rotationTransformMatrix: CGAffineTransform { get }
```

### errorCode

The error code associated with the result should something go wrong during the barcode recognition process. For the full list of possible errors, please visit [`ErrorCode`]({{site.dcvb_enumerations}}core/error-code.html?lang=objc,swift).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSInteger errorCode;
```
2. 
```swift
var errorCode: Int { get }
```

### errorMessage

The error message associated with the error code should something go wrong during the barcode recognition process. For the full list of possible errors, please visit [`ErrorCode`]({{site.dcvb_enumerations}}core/error-code.html?lang=objc,swift).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSString * errorMessage;
```
2. 
```swift
var errorMessage: String? { get }
```
