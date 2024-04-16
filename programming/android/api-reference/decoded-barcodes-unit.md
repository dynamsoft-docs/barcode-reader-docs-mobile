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

The `DecodedBarcodesUnit` class represents a unit that contains decoded barcode elements. It inherits from the [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html) class.

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
| [`getCount`](#getcount) | Get the number of barcodes that are decoded from the image. |
| [`getDecodedBarcode`](#getdecodedbarcode) | Get the barcode that is decoded from the image at the specified index. |
| [`removeAllDecodedBarcodes`](#removalldecodedbarcodes) | Remove all the barcodes that are decoded from the image. |
| [`setDecodedBarcodes`](#setdecodedbarcodes) | Set the barcodes that are decoded from the image. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getDecodedBarcodes

Get all the barcodes that are decoded from the image.

```java
DecodedBarcodeElement[] getDecodedBarcodes();
```

**Return Value**

The barcodes that are decoded from the image.

### getCount

Get the number of barcodes that are decoded from the image.

```java
int getCount();
```

**Return Value**

The number of barcodes that are decoded from the image.

### getDecodedBarcode

Get the `DecodedBarcodeElement` at the specified index.

```java
DecodedBarcodeElement getDecodedBarcode(int index);
```

### removeAllDecodedBarcodes

Remove all the barcodes that are decoded from the image.

```java
void removeAllDecodedBarcodes();
```

### setDecodedBarcode

Set a DecodedBarcodeElement as the decoded barcode of the unit.

```java
int setDecodedBarcode(DecodedBarcodeElement decodedBarcode, Matrix matrixToOriginalImage);
```

**Parameters**

`decodedBarcode`: A `DecodedBarcodeElement` to replace all decoded barcodes of the unit.

`matrixToOriginalImage`: The transformation matrix from the original image to the decoded barcode image.

**Return Value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
