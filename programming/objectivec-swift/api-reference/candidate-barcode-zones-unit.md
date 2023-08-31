---
layout: default-layout
title: DSCandidateBarcodeZonesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSCandidateBarcodeZonesUnit class represents a unit that contains candidate barcode zones unit. It inherits from the DSIntermediateResultUnit class.
keywords: candidate barcode zone, DSCandidateBarcodeZonesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSCandidateBarcodeZonesUnit
permalink: /programming/objectivec-swift/api-reference/candidate-barcode-zones-unit.html
---

# DSCandidateBarcodeZonesUnit Class

The `DSCandidateBarcodeZonesUnit` class represents a unit that contains candidate barcode zones unit. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) -> DSCandidateBarcodeZonesUnit

```cpp
class DSCandidateBarcodeZonesUnit: public DSIntermediateResultUnit
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

[CQuadrilateral]({{ site.dcv_ios_api }}core/basic-structures/quadrilateral.html)
