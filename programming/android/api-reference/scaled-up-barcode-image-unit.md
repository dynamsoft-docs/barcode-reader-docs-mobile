---
layout: default-layout
title: ScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: ScaledUpBarcodeImageUnit class represents a unit that contains scaled up barcode image. It inherits from the IntermediateResultUnit class.
keywords: GetImageData, ScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ScaledUpBarcodeImageUnit
permalink: /programming/android/api-reference/scaled-up-barcode-image-unit.html
---

# ScaledUpBarcodeImageUnit Class

The `ScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ScaledUpBarcodeImageUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getImageData`](#getimagedata) | Gets the image data of the up-scaled barcode. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`clone`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`gethashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit. |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`getType`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`getTransformMatrix`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`EnumTransformMatrixType`]({{site.enums}}core/transform-matrix-type.html). |

### getImageData

Gets the image data of the up-scaled barcode.

```java
ImageData getImageData();
```

**Return value**

An ImageData object as the up-scaled barcode image data.
