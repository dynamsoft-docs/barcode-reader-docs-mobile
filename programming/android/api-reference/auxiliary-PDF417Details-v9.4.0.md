---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the PDF417Details Class of Dynamsoft Barcode Reader for Android SDK.
keywords: PDF417Details, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-PDF417Details.html
---


# PDF417Details

`PDF417Details` is one of the [`detailedResult`](auxiliary-TextResult.md#detailedresult) in class `TextResult`. It stores the PDF417 code details.

```java
class com.dynamsoft.dbr.PDF417Details;
```

| Attribute | Type | Descriptions |
|---------- |------|------------ |
| `moduleSize` | *int* | The barcode module size (the minimum bar width in pixel). |
| `rows` | *int* | The row count of the barcode. |
| `columns` | *int* | The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded. |
| `errorCorrectionLevel` | *int* | The error correction level of the barcode. |

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
