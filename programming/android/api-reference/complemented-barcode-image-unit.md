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

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`clone`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`gethashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit. |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`getType`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`getTransformMatrix`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`EnumTransformMatrixType`]({{site.enums}}/core/transform-matrix-type.html). |

## getImageData

Get the image data of the complemented barcode.

```java
ImageData getImageData();
```

## getLocation

Get the location of the result as a `Quadrilateral` object.

```java
Quadrilateral getLocation();
```
