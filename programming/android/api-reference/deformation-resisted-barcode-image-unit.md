---
layout: default-layout
title: DeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: The DeformationResistedBarcodeImageUnit class represents a unit that contains deformation resisted barcode image data. It inherits from the IntermediateResultUnit class.
keywords: GetImageData, DeformationResistedBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DeformationResistedBarcodeImageUnit
permalink: /programming/android/api-reference/deformation-resisted-barcode-image-unit.html
---

# DeformationResistedBarcodeImageUnit Class

The `DeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DeformationResistedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getDeformationResistedBarcode`](#getdeformationresistedbarcode) | Gets the deformation resisted barcode. |
| [`setDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation resisted barcode. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

## getDeformationResistedBarcode

Gets the deformation resisted barcode.

```java
DeformationResistedBarcode getDeformationResistedBarcode();
```

**Return Value**

Returns a `DeformationResistedBarcode` object as the deformation resisted barcode.

## setDeformationResistedBarcode

Sets the deformation resisted barcode.

```java
int setDeformationResistedBarcode(DeformationResistedBarcode barcode, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] barcode`: A `DeformationResistedBarcode` object as the deformation resisted barcode.

`[in] matrixToOriginalImage`: A `Matrix` object as the transformation matrix.
