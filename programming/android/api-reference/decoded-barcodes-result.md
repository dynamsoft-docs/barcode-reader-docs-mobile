---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Android Edition
description: The DecodedBarcodesResult class of Dynamsoft Barcode Reader Android represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
---

# DecodedBarcodesResult Class

`DecodedBarcodesResult` represents a collection of [`BarcodeResultItems`](barcode-result-item.md), the basic unit of a decoded barcode result. It provides access to information about the decoded barcodes of an image/frame, the source image/frame, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class DecodedBarcodesResult extends CapturedResultBase
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`DecodedBarcodesResult`](#decodedbarcodesresult) | The constructor. |
| [`getItems`](#getitems) | Returns an array of `BarcodeResultItem`, which is the basic unit of the captured results. |

The following methods are inherited from [`CapturedResultBase`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html):

| Method | Description |
| ------ | ----------- |
| [`getOriginalImageHashId`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagehashid) | Gets the hash id of the original image. |
| [`getOriginalImageTag`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html#getoriginalimagetag) | Gets the [ImageTag](image-tag.md) of the original image. |
| [`getRotationTransformMatrix`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html#getrotationtransformmatrix) | Gets the rotation transformation matrix of the original image relative to the rotated image. |
| [`getErrorCode`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html#geterrorcode) | Gets the error code of this result. |
| [`getErrorMessage`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-base.html#geterrormessage) | Gets the error message of this result. |

### DecodedBarcodesResult

The constructor.

```java
DecodedBarcodesResult();
```

### getItems

Returns an array of [`BarcodeResultItem`](barcode-result-item.md), which is the basic unit of the captured results.

```java
BarcodeResultItem[] getItems();
```

**Return Value**

An array of `BarcodeResultItems`.
