---
layout: default-layout
title: DSDecodedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: DSDecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DSDecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDecodedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/decoded-barcodes-unit.html
---

# DSDecodedBarcodesUnit Class

The `DSDecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) -> DSDecodedBarcodesUnit

```cpp
class DSDecodedBarcodesUnit: public DSIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of decoded barcodes in the unit.|
| [`GetDecodedBarcode`](#getdecodedbarcode)           | Gets a pointer to the CDecodedBarcodeElement object at the specified index.|



### GetCount

Gets the number of decoded barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of decoded barcodes in the unit.

### GetDecodedBarcode

Gets a pointer to the CDecodedBarcodeElement object at the specified index.

```cpp
virtual const CDecodedBarcodeElement* GetDecodedBarcode(int index) const = 0;
```

**Parameter**

`[in] index` The index of the desired CDecodedBarcodeElement object.

**Return value**

Returns a pointer to the CDecodedBarcodeElement object at the specified index.

**See Also**

[CDecodedBarcodeElement]({{ site.ios_api }}decoded-barcode-element.html)