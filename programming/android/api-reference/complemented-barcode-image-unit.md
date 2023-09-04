---
layout: default-layout
title: ComplementedBarcodeImageUnit Class - Dynamsoft Barcode Reader Android Edition
description: ComplementedBarcodeImageUnit class represents a unit that contains complemented barcode image data. It inherits from the IntermediateResultUnit class.
keywords: location, ImageData, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ComplementedBarcodeImageUnit
permalink: /programming/android/api-reference/complemented-barcode-image-unit.html
---

# ComplementedBarcodeImageUnit Class

The `ComplementedBarcodeImageUnit` class represents a unit that contains complemented barcode image data. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> ComplementedBarcodeImageUnit

```cpp
class ComplementedBarcodeImageUnit: public IntermediateResultUnit
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

[CQuadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)

### GetImageData

Gets the complemented barcode image data.

```cpp
virtual const CImageData* GetImageData() const = 0;
```

**Return value**

Returns a pointer to the complemented image of the barcode.

**See Also**

[CImageData]({{ site.dcv_android_api }}core/basic-structures/image-data.html)
