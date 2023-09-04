---
layout: default-layout
title: CandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader Android Edition
description: CandidateBarcodeZonesUnit class represents a unit that contains candidate barcode zones unit. It inherits from the IntermediateResultUnit class.
keywords: candidate barcode zone, CandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: CandidateBarcodeZonesUnit
permalink: /programming/android/api-reference/candidate-barcode-zones-unit.html
---

# CandidateBarcodeZonesUnit Class

The `CandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> CandidateBarcodeZonesUnit

```cpp
class CandidateBarcodeZonesUnit: public IntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of candidate barcode zones in the unit.|
| [`GetCandidateBarcodeZone`](#getcandidatebarcodezone)           | Gets the specific candidate barcode zone in the region.|

### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of candidate barcode zones in the unit.


### GetCandidateBarcodeZone

Gets a pointer to a specific candidate barcode zone element.

```cpp
virtual int GetCandidateBarcodeZone(int index, CQuadrilateral *quad) const = 0;
```

**Parameters**
`[in] index` The index of the candidate barcode zone element.
`[out]quad` The quadrilateral of the candidate barcode zone element.

**Return value**

Returns 0 if successful, otherwise returns a negative value.

**See Also**

[CQuadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html)
