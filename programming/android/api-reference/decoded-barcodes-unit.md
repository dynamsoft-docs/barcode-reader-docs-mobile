---
layout: default-layout
title: DecodedBarcodesUnit Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodesUnit class of Dynamsoft Barcode Reader Android represents a unit that contains decoded barcode elements. It inherits from the IntermediateResultUnit class.
keywords: GetCount, GetDecodedBarcode, DecodedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodesUnit
permalink: /programming/android/api-reference/decoded-barcodes-unit.html
---

# DecodedBarcodesUnit Class

`DecodedBarcodesUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which holds the decoded barcodes.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DecodedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getDecodedBarcodes`](#getdecodedbarcodes) | Returns all the barcodes that are decoded from the image. |
| [`getCount`](#getcount) | Returns the number of barcodes that are decoded from the image. |
| [`getDecodedBarcode`](#getdecodedbarcode) | Returns the barcode that is decoded from the image at the specified index. |
| [`removeAllDecodedBarcodes`](#removealldecodedbarcodes) | Remove all the barcodes that are decoded from the image. |
| [`setDecodedBarcode`](#setdecodedbarcode) | Set the barcodes that are decoded from the image. |

The following methods are inherited from [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getDecodedBarcodes

Returns all the barcodes that are decoded from the image as an array of [`DecodedBarcodeElement`](decoded-barcode-element.md).

```java
DecodedBarcodeElement[] getDecodedBarcodes();
```

**Return Value**

An array of [`DecodedBarcodeElement`](decoded-barcode-element.md) as the decoded barcodes.

### getCount

Returns the number of barcodes that are decoded from the image.

```java
int getCount();
```

**Return Value**

An integer representing the number of barcodes that are decoded from the image.

### getDecodedBarcode

Returns the [`DecodedBarcodeElement`](decoded-barcode-element.md) at the specified index. This is the same as accessing the same index of the result array from [`getDecodedBarcodes`](#getdecodedbarcodes).

```java
DecodedBarcodeElement getDecodedBarcode(int index);
```

**Parameters**

`[in] index`: The index of the decoded barcode from the array of decoded barcodes.

**Return Value**

A [`DecodedBarcodeElement`](decoded-barcode-element.md) representing the decoded barcode.

### removeAllDecodedBarcodes

Removes all the [`DecodedBarcodeElement`](decoded-barcode-element.md) from the `DecodedBarcodesUnit`.

```java
void removeAllDecodedBarcodes();
```

### setDecodedBarcode

Set the [`DecodedBarcodeElement`](decoded-barcode-element.md) of the `DecodedBarcodesUnit`.

```java
int setDecodedBarcode(DecodedBarcodeElement element, Matrix matrixToOriginalImage);
```

**Parameters**

`decodedBarcode`: A `DecodedBarcodeElement` to replace all the decoded barcodes of the unit.

`matrixToOriginalImage`: The transformation matrix to convert the decoded barcode object to the original image.

**Return Value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
