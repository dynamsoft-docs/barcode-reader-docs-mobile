---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: ComplementedBarcodeImageUnit class of Dynamsoft Barcode Reader Android represents a unit that contains complemented barcode image data. It inherits from the IntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ComplementedBarcodeImageUnit
---

# ComplementedBarcodeImageUnit Class

`ComplementedBarcodeImageUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the complemented barcode image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ComplementedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getImageData`](#getimagedata) | Returns the `ImageData` of the complemented barcode.|
| [`getLocation`](#getlocation) | Returns the location of the complemented barcode.|
| [`setLocation`](#setlocation) | Sets the location of the complemented barcode.|

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getImageData

Returns the [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) of the complemented barcode.

```java
ImageData getImageData();
```

**Return Value**

An [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) object.

### getLocation

Returns the location of the complemented barcode as a [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html).

```java
Quadrilateral getLocation();
```

**Return Value**

A [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html) object representing the location.
### setLocation

Sets the location of the complemented barcode within the original image.

```java
int setLocation(Quadrilateral location, Matrix matrixToOriginalImage);
```

**Parameters**

`location`: The location of the complemented barcode as a [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html) object.

`matrixToOriginalImage`: The transformation `Matrix` of the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
