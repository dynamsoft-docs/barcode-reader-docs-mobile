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

The `DeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> DeformationResistedBarcodeImageUnit

```cpp
class DeformationResistedBarcodeImageUnit: public IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetImageData`](#getimagedata)           | Gets the deformation resisted barcode image data.|


### GetImageData

Gets the deformation resisted barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the deformation resisted barcode image data.

**See Also**

[CImageData]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
