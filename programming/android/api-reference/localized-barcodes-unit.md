---
layout: default-layout
title: LocalizedBarcodesUnit Class - Dynamsoft Barcode Reader Android Edition
description: The LocalizedBarcodesUnit class of Dynamsoft Barcode Reader Android represents a unit that contains localized barcodes unit. It inherits from the IntermediateResultUnit class.
keywords: GetCount, GetLocalizedBarcode, LocalizedBarcodesUnit, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: LocalizedBarcodesUnit
---

# LocalizedBarcodesUnit Class

`LocalizedBarcodesUnit` extends the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class and represents a unit which contains localized barcodes.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class LocalizedBarcodesUnit extends IntermediateResultUnit
```

## Methods

| Method | Description |
|--------|-------------|
| [`getLocalizedBarcodes`](#getlocalizedbarcodes) | Returns an array of `LocalizedBarcodeElement`. |
| [`getCount`](#getcount) | Returns the number of localized barcodes in the unit. |
| [`getLocalizedBarcode`](#getlocalizedbarcode) | Returns the `LocalizedBarcodeElement` at the specified index. |
| [`removeAllLocalizedBarcodes`](#removealllocalizedbarcodes) | Removes all the localized barcodes in the unit. |
| [`removeLocalizedBarcode`](#removelocalizedbarcode) | Removes the `LocalizedBarcodeElement` at the specified index from the unit. |
| [`addLocalizedBarcode`](#addlocalizedbarcode) | Add a new `LocalizedBarcodeElement` to the unit. |
| [`setLocalizedBarcode`](#setlocalizedbarcode) | Set a `LocalizedBarcodeElement` at the specified index. |

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getLocalizedBarcodes

Returns an array of [`LocalizedBarcodeElement`](localized-barcode-element.md), which contains the detailed information for each localized barcode.

```java
LocalizedBarcodeElement[] getLocalizedBarcodes()
```

**Return value**

An array of [`LocalizedBarcodeElement`](localized-barcode-element.md), which contains the detailed information for each localized barcode.

### getCount

Returns the number of localized barcodes ([`LocalizedBarcodeElement`](localized-barcode-element.md)) in the unit.

```java
int getCount()
```

**Return Value**

The number of localized barcodes.

### getLocalizedBarcode

Returns the [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

```java
LocalizedBarcodeElement getLocalizedBarcode(int index)
```

**Parameters**

`[in] index`: The index of the localized barcode element.

**Return value**

The [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

### removeAllLocalizedBarcodes

Removes all the localized barcodes in the unit.

```java
void removeAllLocalizedBarcodes()
```

### removeLocalizedBarcode

Removes the [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index from the unit.

```java
int removeLocalizedBarcode(int index)
```

**Parameters**

`[in] index`: The index of the localized barcode element.

**Return value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### addLocalizedBarcode

Add a new [`LocalizedBarcodeElement`](localized-barcode-element.md) to the unit.

```java
int addLocalizedBarcode(LocalizedBarcodeElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] element`: The `LocalizedBarcodeElement` to be added.

`[in] matrixToOriginalImage`: The transformation `Matrix` of the original image.

**Return value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.

### setLocalizedBarcode

Set a [`LocalizedBarcodeElement`](localized-barcode-element.md) at the specified index.

```java
int setLocalizedBarcode(int index, LocalizedBarcodeElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] index`: The index where the localized barcode element will be set.

`[in] element`: The `LocalizedBarcodeElement` to be set.

`[in] matrixToOriginalImage`: The transformation `Matrix` of the original image.

**Return value**

Returns the `ErrorCode` if it fails. Otherwise, returns 0.
