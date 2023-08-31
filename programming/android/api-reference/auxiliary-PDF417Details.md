---
layout: default-layout
title: DSPDF417Details Class - Dynamsoft Barcode Reader Android Edition
description: The DSPDF417Details class represents a barcode in PDF417 format. It inherits from the DSBarcodeDetails class and contains information about the row count, column count, and error correction level of the barcode.
keywords: DSPDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSPDF417Details
permalink: /programming/android/api-reference/auxiliary-PDF417Details.html
---

# DSPDF417Details

The `CPDF417Details` class represents a barcode in PDF417 format. It inherits from the `CBarcodeDetails` class and contains information about the row count, column count, and error correction level of the barcode.

```java
class com.dynamsoft.dbr.PDF417Details;
```

| Attribute | Type | Descriptions |
|---------- |------|------------ |
| [`moduleSize`](#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *int* | The row count of the barcode. |
| [`columns`](#columns) | *int* | The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* | The error correction level of the barcode. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *int* | Indicates whether the PDF417 barcode has a left row indicator. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *int* | Indicates whether the PDF417 barcode has a right row indicator. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int moduleSize
```

## rows

The row count of the barcode.

```java
int rows
```

## columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

```java
int columns
```

## errorCorrectionLevel

The error correction level of the barcode.

```java
int errorCorrectionLevel
```

## hasLeftRowIndicator

Indicates whether the PDF417 barcode has a left row indicator.

```java
int hasLeftRowIndicator
```

## hasRightRowIndicator

Indicates whether the PDF417 barcode has a right row indicator.

```java
int hasRightRowIndicator
```
