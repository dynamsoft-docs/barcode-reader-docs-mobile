---
layout: default-layout
title: DeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: The DeformationResistedBarcodeImageUnit class of Dynamsoft Barcode Reader Android represents a unit that contains deformation resisted barcode image data. It inherits from the IntermediateResultUnit class.
keywords: GetImageData, DeformationResistedBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DeformationResistedBarcodeImageUnit
permalink: /programming/android/api-reference/deformation-resisted-barcode-image-unit.html
---

# DeformationResistedBarcodeImageUnit Class

`DeformationResistedBarcodeImageUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the deformation-resisted barcode, including corresponding image data, its location, and the barcode format.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DeformationResistedBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getDeformationResistedBarcode`](#getdeformationresistedbarcode) | Returns the deformation-resisted barcode. |
| [`setDeformationResistedBarcode`](#setdeformationresistedbarcode) | Sets the deformation-resisted barcode onto the original image. |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getDeformationResistedBarcode

Returns the deformation-resisted barcode as a [`DeformationResistedBarcode`](deformation-resisted-barcode.md) object.

```java
DeformationResistedBarcode getDeformationResistedBarcode();
```

**Return Value**

A [`DeformationResistedBarcode`](deformation-resisted-barcode.md) object representing the deformation-resisted barcode.

### setDeformationResistedBarcode

Sets the deformation-resisted barcode onto the original image using a transformation matrix.

```java
int setDeformationResistedBarcode(DeformationResistedBarcode barcode, Matrix matrixToOriginalImage);
```

**Parameters**

`[in] barcode`: A [`DeformationResistedBarcode`](deformation-resisted-barcode.md) object as the deformation-resisted barcode.

`[in] matrixToOriginalImage`: A `Matrix` object as the transformation matrix to the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
