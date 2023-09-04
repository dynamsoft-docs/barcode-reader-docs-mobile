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

The `ScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `IntermediateResultUnit` class.

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

### getImageData

Gets the image data of the up-scaled barcode.

```java
ImageData getImageData();
```

**Return value**

An ImageData object as the up-scaled barcode image data.
