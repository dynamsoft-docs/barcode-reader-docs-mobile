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

The `DSDecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

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
| [`originalImageHashId`](#originalimagehashid) | *NSString \** | The hash id of the source image. You can use this ID to get the source image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`originalImageTag`](#originalimagetag) | *DSImageTag \** | The tag of the source image. |
| [`items`](#items) | *NSArray<DSBarcodeResultItem\*> \** | An array of DSBarcodeResultItems, which are the basic unit of the captured results. |
| [`rotationTransformMatrix`](#rotationtransformmatrix) | *CGAffineTransform* |Get the rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`](#errorcode) | *NSInteger* | Get the error code of this result. |
| [`errorMessage`](#errormessage) | *NSString \** | Get the error message of this result. |

## originalImageHashId

The hash id of the source image. You can use this ID to get the source image via [`DSIntermediateResultManager`]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-manager.html) class.

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

Returns the [`ImageTag`]({{ site.dcv_ios_api }}core/basic-structures/image-tag.html) of the source image. The image tag contains info about the image such as the image ID and the image capture distance mode.

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

## items

An array of [DSBarcodeResultItem](barcode-result-item.md), which is the basic unit of the barcode captured results.

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

## rotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

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

Returns the error code of this result should something go wrong. A `DecodedBarcodesResult` will carry error information when the license module is missing or the process times out.

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

Returns the error message of this result should something go wrong. A `DecodedBarcodesResult` will carry error information when the license module is missing or the process times out.

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
