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

The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `IntermediateResultUnit` class.

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
