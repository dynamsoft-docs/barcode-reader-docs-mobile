---
layout: default-layout
title: DSComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSComplementedBarcodeImageUnit class represents a unit that contains complemented barcode image data. It inherits from the DSIntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSComplementedBarcodeImageUnit
permalink: /programming/objectivec-swift/api-reference/complemented-barcode-image-unit.html
---

# DSComplementedBarcodeImageUnit Class

The `DSComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) -> DSComplementedBarcodeImageUnit

```cpp
class DSComplementedBarcodeImageUnit: public DSIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetLocation`](#getlocation) | Get the location of the complemented barcode in a quadrilateral.|
| [`GetImageData`](#getimagedata) | Gets the complemented barcode image data.|

### GetLocation

Get the location of the complemented barcode in a quadrilateral.

```cpp
virtual CQuadrilateral GetLocation() const = 0;
```

**Return value**

Returns the location of the complemented barcode in a quadrilateral.

**See Also**

[CQuadrilateral]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html)

### GetImageData

Gets the complemented barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the complemented image of the barcode.

**See Also**

[CImageData]({{ site.dcv_ios_api }}core/basic-structures/image-data.html)
