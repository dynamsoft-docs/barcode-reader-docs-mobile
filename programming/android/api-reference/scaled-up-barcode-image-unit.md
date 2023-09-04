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

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> ScaledUpBarcodeImageUnit

```cpp
class ScaledUpBarcodeImageUnit: public IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the scaled up barcode image data.|


### GetImageData

Gets the scaled up barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the scaled up image of the barcode.

**See Also**

[CImageData]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
