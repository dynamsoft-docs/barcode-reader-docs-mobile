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

The `LocalizedBarcodesUnit` class represents a unit that contains localized barcodes unit. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

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

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

| Method | Description |
|------- |-------------|
| [`clone`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#clone) | Creates a copy of the intermediate result unit. |
| [`gethashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gethashid) | Gets the hash ID of the unit. |
| [`getOriginalImageHashId`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagehashid) | Gets the hash ID of the original image. You can use this ID to get the original image via [`IntermediateResultManager`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-manager.html) class. |
| [`getOriginalImageTag`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#getoriginalimagetag) | Gets the image tag of the original image. |
| [`getType`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettype) | Gets the type of the intermediate result unit. |
| [`getTransformMatrix`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html#gettransformmatrix) | Gets the transformation matrix via [`EnumTransformMatrixType`]({{site.enums}}/core/transform-matrix-type.html). |

### getLocalizedBarcodes

Get an array of [`LocalizedBarcodeElement`](localized-barcode-element.md), which contains the detailed information of each localized barcode.

```java
LocalizedBarcodeElement[] getLocalizedBarcodes()
```

**Return value**

An array of `LocalizedBarcodeElement`, which contains the detailed information of each localized barcode.

**See Also**

[LocalizedBarcodeElement](localized-barcode-element.html)
