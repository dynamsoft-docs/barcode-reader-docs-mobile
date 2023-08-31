---
layout: default-layout
title: DSScaledUpBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: DSScaledUpBarcodeImageUnit class represents a unit that contains scaled up barcode image. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSScaledUpBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSScaledUpBarcodeImageUnit
permalink: /programming/android/api-reference/scaled-up-barcode-image-unit.html
---

# DSScaledUpBarcodeImageUnit Class

The `DSScaledUpBarcodeImageUnit` class represents a unit that contains scaled up barcode image. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> DSScaledUpBarcodeImageUnit

```cpp
class DSScaledUpBarcodeImageUnit: public DSIntermediateResultUnit
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
