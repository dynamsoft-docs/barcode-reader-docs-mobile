---
layout: default-layout
title: LocalizedBarcodesUnit Class - Dynamsoft Barcode Reader Android Edition
description: The LocalizedBarcodesUnit class represents a unit that contains localized barcodes unit. It inherits from the IntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, LocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: LocalizedBarcodesUnit
permalink: /programming/android/api-reference/localized-barcodes-unit.html
---

# LocalizedBarcodesUnit Class

The `LocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the `IntermediateResultUnit` class.

## Definition

*Namespace:* dynamsoft::dbr::intermediate_results

*Assembly:* DynamsoftBarcodeReader

*Inheritance:* [IntermediateResultUnit]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) -> LocalizedBarcodesUnit

```cpp
class LocalizedBarcodesUnit: public IntermediateResultUnit
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

[CLocalizedBarcodeElement]({{ site.android_api }}localized-barcode-element.html)
