---
layout: default-layout
title: DecodedBarcodesResult Class - Dynamsoft Barcode Reader Android Edition
description: The DecodedBarcodesResult class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.
keywords: GetOriginalImageHashId, GetItemsCount, GetErrorCode, DecodedBarcodesResult, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesResult
permalink: /programming/android/api-reference/decoded-barcodes-result.html
---

# DecodedBarcodesResult Class

`DecodedBarcodesResult` represents a collection of [`BarcodeResultItems`](barcode-result-item.md), the basic unit of a decoded barcode result. It provides access to information about the decoded barcodes of an image/frame, the source image/frame, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class DecodedBarcodesResult
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getItems`](#getitems) | Returns an array of `BarcodeResultItem`, which is the basic unit of the captured results. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | Returns the rotation transformation matrix of the original image relative to the rotated image. |
| [`getOriginalImageHashId`](#getoriginalimagehashid) | Returns the hash ID of the source image. |
| [`getOriginalImageTag`](#getoriginalimagetag) | Returns the `ImageTag` of the source image. |
| [`getErrorCode`](#geterrorcode) | Returns the error code should something go wrong during the barcode recognition process. |
| [`getErrorMessage`](#geterrormessage) | Returns the error message associated with the error code should something go wrong during the barcode recognition process. |

### getItems

Returns an array of [`BarcodeResultItem`](barcode-result-item.md), which is the basic unit of the captured results.

```java
BarcodeResultItem[] getItems();
```

**Return Value**

An array of `BarcodeResultItems`.

### getRotationTransformMatrix

Returns the rotation transformation matrix of the original image relative to the rotated image.

```java
Matrix getRotationTransformMatrix();
```

**Return Value**

A [Matrix](https://developer.android.com/reference/android/opengl/Matrix){:target="_blank"} object representing the rotation transformation matrix

### getOriginalImageHashId

Returns the hash ID of the original image. You can use this ID to get the original image via the [`IntermediateResultManager`]({{ site.dcv_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html) class.

```java
String getOriginalImageHashId();
```

**Return Value**

The hash id of the source image.

### getOriginalImageTag

Returns the [`ImageTag`]({{ site.dcv_android_api }}core/basic-structures/image-tag.html) of the source image. The image tag contains info about the image such as the image ID and the image capture distance mode.

```java
ImageTag getOriginalImageTag();
```

**Return Value**

The `ImageTag` of the source image.

### getErrorCode

Returns the error code should something go wrong during the barcode recognition process. For the full list of possible errors, please visit [`ErrorCode`]({{site.dcv_enumerations}}core/error-code.html?lang=android).

```java
int getErrorCode();
```

**Return Value**

An integer representing a `EnumErrorCode`.

### getErrorMessage

Returns the error message associated with the error code should something go wrong during the barcode recognition process. For the full list of possible errors, please visit [`ErrorCode`]({{site.dcv_enumerations}}core/error-code.html?lang=android).

```java
String getErrorMessage();
```

**Return Value**

A string representing the message of a `EnumErrorCode`.

