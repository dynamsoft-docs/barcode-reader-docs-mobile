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

The `DecodedBarcodesResult` class represents the result of a barcode reading process. It provides access to information about the decoded barcodes, the source image, and any errors that occurred during the barcode reading process.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class DecodedBarcodesResult
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getItems`](#getitems) | Get an array of `BarcodeResultItems`, which are the basic unit of the captured results. |
| [`getRotationTransformMatrix`](#getrotationtransformmatrix) | Get the rotation transformation matrix of the original image relative to the rotated image. |
| [`getOriginalImageHashId`](#getoriginalimagehashid) | Get the hash id of the source image. You can use this ID to get the source image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`getOriginalImageTag`](#getoriginalimagetag) | Get the tag of the source image. |
| [`getErrorCode`](#geterrorcode) | Get the error code if an error occurs when processing the image. |
| [`getErrorMessage`](#geterrormessage) | Get the error message if an error occurs when processing the image. |

### getItems

Get an array of `BarcodeResultItems`, which are the basic unit of the captured results.

```java
BarcodeResultItem[] getItems();
```

**Return Value**

An array of `BarcodeResultItems`.

### getRotationTransformMatrix

Get the rotation transformation matrix of the original image relative to the rotated image.

```java
CGAffineTransform getRotationTransformMatrix();
```

**Return Value**

The rotation transformation matrix

### getOriginalImageHashId

Get the hash id of the source image. You can use this ID to get the source image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class.

```java
String getOriginalImageHashId();
```

**Return Value**

The hash id of the source image.

### getOriginalImageTag

Get the tag of the source image.

```java
ImageTag getOriginalImageTag();
```

**Return Value**

The tag of the source image.

### getErrorCode

Get the error code if an error occurs when processing the image.

```java
int getErrorCode();
```

### getErrorMessage

Get the error message if an error occurs when processing the image.

```java
String getErrorMessage();
```
