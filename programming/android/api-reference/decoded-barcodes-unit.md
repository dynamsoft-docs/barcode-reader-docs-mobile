---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the IntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesUnit
permalink: /programming/android/api-reference/decoded-barcodes-unit.html
---

# DecodedBarcodesUnit Class

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DecodedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getDecodedBarcodes`](#getdecodedbarcodes) | Get all the barcodes that are decoded from the image. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`clone`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`gethashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit. |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]() class. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`getType`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`getTransformMatrix`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`EnumTransformMatrixType`]({{site.dcv_enumerations}}core/transform-matrix-type.html). |

### getDecodedBarcodes

Get all the barcodes that are decoded from the image.

```java
DecodedBarcodeElement[] getDecodedBarcodes();
```

**Return Value**

The barcodes that are decoded from the image.
