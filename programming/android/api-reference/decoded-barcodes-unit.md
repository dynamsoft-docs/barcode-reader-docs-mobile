---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodesUnit class represents a unit that contains decoded barcode elements. It inherits from the IntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesUnit
permalink: /programming/android/api-reference/decoded-barcodes-unit.html
---

# DecodedBarcodesUnit Class

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> DecodedBarcodesUnit

```cpp
class DecodedBarcodesUnit: public IntermediateResultUnit
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

[CDecodedBarcodeElement]({{ site.android_api }}decoded-barcode-element.html)