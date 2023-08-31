---
layout: default-layout
title: DSLocalizedBarcodesUnit Class - Dynamsoft Barcode Reader iOS Edition
description: The DSLocalizedBarcodesUnit class represents a unit that contains localized barcodes unit. It inherits from the DSIntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, DSLocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSLocalizedBarcodesUnit
permalink: /programming/objectivec-swift/api-reference/localized-barcodes-unit.html
---

# DSLocalizedBarcodesUnit Class

The `DSLocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `DSIntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [DSIntermediateResultUnit]({{ site.dcv_ios_api }}core/intermediate-results/intermediate-result-unit.html) -> DSLocalizedBarcodesUnit

```cpp
class DSLocalizedBarcodesUnit: public DSIntermediateResultUnit
```

## Methods

| Method                            | Description |
|-----------------------------------|-------------|
| [`GetCount`](#getcount)           | Gets the number of localized barcodes in the unit.|
| [`GetLocalizedBarcode`](#getlocalizedbarcode)           | Gets a pointer to a specific localized barcode element.|

### GetCount

Gets the number of localized barcodes in the unit.

```cpp
virtual int GetCount() const = 0;
```

**Return value**

Returns the number of localized barcodes in the unit.


### GetLocalizedBarcode

Gets a pointer to a specific localized barcode element.

```cpp
virtual const CLocalizedBarcodeElement* GetLocalizedBarcode(int index) const = 0;
```

**Parameters**
`[in] index` The index of the localized barcode element to retrieve.

**Return value**

Returns a const pointer to the localized barcode element at the specified index.

**See Also**

[CLocalizedBarcodeElement]({{ site.ios_api }}localized-barcode-element.html)
