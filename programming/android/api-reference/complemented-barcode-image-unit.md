---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: ComplementedBarcodeImageUnit class represents a unit that contains complemented barcode image data. It inherits from the IntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ComplementedBarcodeImageUnit
permalink: /programming/android/api-reference/complemented-barcode-image-unit.html
---

# ComplementedBarcodeImageUnit Class

The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ComplementedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getImageData`](#getimagedata) | The image data of the complemented barcode.|
| [`getLocation`](#getlocation) | The location of the result as a `Quadrilateral` object.|
| [`setLocation`](#setlocation) | Sets the location of the result as a `Quadrilateral` object.|

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getImageData

Get the image data of the complemented barcode.

```java
ImageData getImageData();
```

### getLocation

Get the location of the result as a `Quadrilateral` object.

```java
Quadrilateral getLocation();
```

### setLocation

Sets the location of the result as a `Quadrilateral` object.

```java
int setLocation(Quadrilateral location, Matrix matrixToOriginalImage);
```

**Parameters**

`location`: The location of the result as a `Quadrilateral` object.

`matrixToOriginalImage`: The transformation matrix from the original image to the complemented barcode image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
