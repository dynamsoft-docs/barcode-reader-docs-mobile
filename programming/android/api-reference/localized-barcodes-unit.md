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

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class LocalizedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
|--------|-------------|
| [`getLocalizedBarcodes`](#getlocalizedbarcodes) | Gets a pointer to a specific localized barcode element.|

### getLocalizedBarcodes

Get an array of `LocalizedBarcodeElement`, which contains the detailed information of each localized barcode.

```java
LocalizedBarcodeElement[] getLocalizedBarcodes()
```

**Return value**

An array of `LocalizedBarcodeElement`, which contains the detailed information of each localized barcode.

**See Also**

[LocalizedBarcodeElement](localized-barcode-element.html)
