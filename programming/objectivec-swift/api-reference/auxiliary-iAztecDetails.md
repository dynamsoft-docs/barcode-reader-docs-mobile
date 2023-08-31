---
layout: default-layout
title: DSAztecDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSAztecDetails class represents a barcode in Aztec format. It inherits from the DSBarcodeDetails class and contains information about the row count, column count, and layer number of the barcode.
keywords: DSAztecDetails, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSAztecDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-AztecDetails.html
---

# DSAztecDetails

The `DSAztecDetails` class represents a barcode in Aztec format. It inherits from the `DSBarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

```java
class com.dynamsoft.dbr.AztecDetails;
```

| Attribute | Type | Descriptions |
|---------- | -----|------ |
| [`moduleSize`](#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *int* | The row count of the barcode. |
| [`columns`](#columns) | *int* | The column count of the barcode. |
| [`layerNumber`](#layernumber) | *int* | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

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

The column count of the barcode.

```java
int columns
```  

## layerNumber

A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code.  

```java
int layerNumber
```
