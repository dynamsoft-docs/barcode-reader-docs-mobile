---
layout: default-layout
title: DSDeformationResistedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSDeformationResistedBarcodeImageUnit class represents a unit that contains deformation resisted barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: GetImageData, DSDeformationResistedBarcodeImageUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDeformationResistedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/deformation-resisted-barcode-image-unit.html
---

# DSDeformationResistedBarcodeImageUnit Class

The `DSDeformationResistedBarcodeImageUnit` class represents a unit that contains deformation resisted barcode image data. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) -> DSDeformationResistedBarcodeImageUnit

```cpp
class DSDeformationResistedBarcodeImageUnit: public DSIntermediateResultUnit
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

[CImageData]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)
