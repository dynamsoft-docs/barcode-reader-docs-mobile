---
layout: default-layout
title: DeformationResistedBarcode Class - Dynamsoft Barcode Reader Android Edition
description: The DeformationResistedBarcode class represents the information of a deformation resisted barcode with the image data, location and format.
keywords: GetImageData, DeformationResistedBarcode, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DeformationResistedBarcode
permalink: /programming/android/api-reference/deformation-resisted-barcode.html
---

# DeformationResistedBarcode Class

The `DeformationResistedBarcode` class represents a unit that contains deformation resisted barcode image data. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DeformationResistedBarcode
```

## Attributes

| Attribute | Description |
| ------ | ----------- |
| [`imageData`](#imagedata) | The deformation resisted barcode image data. |
| [`location`](#location) | The location of the deformation resisted barcode. |
| [`format`](#format) | The format of the deformation resisted barcode. |

### imageData

An `ImageData` object as the image data of the deformation resisted barcode.

```java
ImageData imageData;
```

### location

A `Quadrilateral` object as the location of the deformation resisted barcode.

```java
Quadrilateral location;
```

### format

The format of the deformation resisted barcode.

```java
long format;
```
