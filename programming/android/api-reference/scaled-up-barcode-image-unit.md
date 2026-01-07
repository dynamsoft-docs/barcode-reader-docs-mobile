---
layout: default-layout
title: ScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: ScaledUpBarcodeImageUnit class of Dynamsoft Barcode Reader Android represents a unit that contains scaled up barcode image. It inherits from the IntermediateResultUnit class.
keywords: GetImageData, ScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ScaledUpBarcodeImageUnit
permalink: /programming/android/api-reference/scaled-up-barcode-image-unit.html
---

# ScaledUpBarcodeImageUnit Class

`ScaledUpBarcodeImageUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which contains a scaled-up barcode image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ScaledUpBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getImageData`](#getimagedata) | Returns the `ImageData` of the scaled-up barcode image. |
| [`setImageData`](#setimagedata) | Sets the scaled-up barcode image of the unit. |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getImageData

Returns the [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) of the scaled-up barcode image.

```java
ImageData getImageData();
```

**Return value**

A `ImageData` object representing the scaled-up barcode image.

### setImageData

Sets the scaled-up barcode image of the unit.

```java
int setImageData(ImageData imageData);
```

**Parameters**

`[in] imageData` An [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) object which represents the scaled-up barcode image.

**Return value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
