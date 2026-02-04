---
layout: default-layout
title: DSDecodedBarcodesResult Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDecodedBarcodesResult class of Dynamsoft Barcode Reader iOS represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DSDecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesResult
---

# DSDecodedBarcodesResult Class

`DSDecodedBarcodesResult` represents a collection of [`DSBarcodeResultItem`](barcode-result-item.md), the basic unit of a decoded barcode result. It provides access to information about the decoded barcodes of an image/frame, the source image/frame, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDecodedBarcodesResult : DSCapturedResultBase
```
2. 
```swift
class DecodedBarcodesResult : CapturedResultBase
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`items`](#items) | *NSArray<DSBarcodeResultItem\*> \** | An array of `DSBarcodeResultItem`, which is the basic unit of the captured results. |

The following attributes are inherited from [`DSCapturedResultBase`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html):

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`originalImageHashId`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html#originalimagehashid) | *NSString \** | The hash id of the original image. |
| [`originalImageTag`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html#originalimagetag) | *DSImageTag \** | The [DSImageTag](image-tag.md) of the original image. |
| [`rotationTransformMatrix`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html#rotationtransformmatrix) | *CGAffineTransform* | The rotation transformation matrix of the original image relative to the rotated image. |
| [`errorCode`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html#errorcode) | *NSInteger* | Get the error code of this result. |
| [`errorMessage`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-base.html#errormessage) | *NSString \** | Get the error message of this result. |

## items

An array of [`DSBarcodeResultItem`](barcode-result-item.md), which is the basic unit of the barcode capture results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, copy, nullable) NSArray<DSBarcodeResultItem *> *items;
```
2. 
```swift
var items: [DSBarcodeResultItem]? { get }
```
