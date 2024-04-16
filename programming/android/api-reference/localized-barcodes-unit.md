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
| [`getCount`](#getcount) | Gets the number of localized barcodes in the unit. |
| [`getLocalizedBarcode`](#getlocalizedbarcode) | Gets a pointer to a specific localized barcode element. |
| [`removeAllLocalizedBarcodes`](#removealllocalizedbarcodes) | Removes all localized barcodes in the unit. |
| [`removeLocalizedBarcode`](#removelocalizedbarcode) | Removes a localized barcode in the unit. |
| [`addLocalizedBarcode`](#addlocalizedbarcode) | Adds a localized barcode in the unit. |
| [`setLocalizedBarcode`](#setlocalizedbarcode) | Sets a localized barcode in the unit. |

## Inherited Methods

The following methods are inherited from class [`IntermediateResultUnit`]({{ site.dcv_android_api }}core/intermediate-results/intermediate-result-unit.html).

{%- include api-reference/intermediate-result-unit-android.md -%}

### getLocalizedBarcodes

Get an array of [`LocalizedBarcodeElement`](localized-barcode-element.md), which contains the detailed information of each localized barcode.

```java
LocalizedBarcodeElement[] getLocalizedBarcodes()
```

**Return value**

An array of `LocalizedBarcodeElement`, which contains the detailed information of each localized barcode.

**See Also**

[LocalizedBarcodeElement](localized-barcode-element.html)

### getCount

Get the number of `LocalizedBarcodeElement` in the unit.

```java
int getCount()
```

### getLocalizedBarcode

Get the `LocalizedBarcodeElement` at the specified index.

```java
LocalizedBarcodeElement getLocalizedBarcode(int index)
```

**Parameters**

`[in] index`: The index of the localized barcode element.

**Return value**

The `LocalizedBarcodeElement` at the specified index.

### removeAllLocalizedBarcodes

Remove all localized barcodes.

```java
void removeAllLocalizedBarcodes()
```

### removeLocalizedBarcode

Remove the `LocalizedBarcodeElement` at the specified index.

```java
int removeLocalizedBarcode(int index)
```

**Parameters**

`[in] index`: The index of the localized barcode element.

**Return value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### addLocalizedBarcode

Add a `LocalizedBarcodeElement` to the unit.

```java
int addLocalizedBarcode(LocalizedBarcodeElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] element`: The `LocalizedBarcodeElement` to be added.

`[in] matrixToOriginalImage`: The transformation matrix of the original image.

**Return value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.

### setLocalizedBarcode

Set a `LocalizedBarcodeElement` at the specified index.

```java
int setLocalizedBarcode(int index, LocalizedBarcodeElement element, Matrix matrixToOriginalImage)
```

**Parameters**

`[in] index`: The index of the localized barcode element.

`[in] element`: The `LocalizedBarcodeElement` to be set.

`[in] matrixToOriginalImage`: The transformation matrix of the original image.

**Return value**

Returns the `ErrorCode` if failed. Otherwise, returns 0.
