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

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DecodedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getDecodedBarcodes`](#getdecodedbarcodes) | Get all the barcodes that are decoded from the image. |

### getDecodedBarcodes

Get all the barcodes that are decoded from the image.

```java
DecodedBarcodeElement[] getDecodedBarcodes();
```

**Return Value**

The barcodes that are decoded from the image.
