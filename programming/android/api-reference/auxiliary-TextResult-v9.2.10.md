---
layout: default-layout
title: TextResult Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the TextResult Class of Dynamsoft Barcode Reader for Android SDK.
keywords: TextResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-TextResult-v9.2.10.html
---

# TextResult

Stores the text result.

```java
class com.dynamsoft.dbr.TextResult;
```

| Attribute | Type | Descriptions |
| --------- | ---- | ------------ |
| [`barcodeFormat`](#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormatString`](#barcodeformatstring) | *String* | Barcode type in BarcodeFormat group 1 as string. |
| [`barcodeFormat_2`](#barcodeformat_2) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString_2`](#barcodeformatstring_2) | *String* | Barcode type in BarcodeFormat group 2 as string. |
| [`barcodeText`](#barcodetext) | *String* | The barcode text, ends by '\0'. |
| [`barcodeBytes`](#barcodebytes) | *byte\[\]* | The barcode content in a byte array. |
| [`localizationResult`](#localizationresult) | [`LocalizationResult`](auxiliary-LocalizationResult.md)\* | The corresponding localization result. |
| [`detailedResult`](#detailedresult) | *Object* | One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.md), [`PDF417Details`](auxiliary-PDF417Details.md), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md), [`AztecDetails`](auxiliary-AztecDetails.md), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.md). |
| [`results`](#results) | [`ExtendedResult`](auxiliary-ExtendedResult.md)\[\] | The extended result array. |
| [`exception`](#exception) | *String* | The exception message. |
| [`isMirrored`](#ismirrored) | *int* | This attribute stands for whether the barcode is mirrored. |
| [`isDPM`](#isdpm) | *int* | This attribute stands for whether the barcode is recognized by DPM mode. |

## barcodeFormat

Barcode type in BarcodeFormat group 1.

```java
int barcodeFormat
```

**Value Range**

One of the [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) Enumeration value.

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## barcodeFormatString

Barcode type in BarcodeFormat group 1 as string.

```java
String barcodeFormatString
```

**Value Range**

One of the barcode type in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android).

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```java
int barcodeFormat_2
```

**Value Range**

One of the [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android) Enumeration items

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## barcodeFormatString_2

Barcode type in BarcodeFormat group 2 as string.

```java
String barcodeFormatString_2
```

**Value Range**

One of the barcode type in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android).

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## barcodeText

The text barcode decoding result. Ends by '\0'.

```java
String barcodeText
```

## barcodeBytes

The barcode content in a byte array.

```java
byte[] barcodeBytes
```

## localizationResult

The corresponding localization result.

```java
LocalizationResult localizationResult
```

## detailedResult

One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.md), [`PDF417Details`](auxiliary-PDF417Details.md), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md), [`AztecDetails`](auxiliary-AztecDetails.md), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.md).

```java
Object detailedResult
```

## results

The extended result array.

```java
ExtendedResult[] results
```

## exception

The exception message.

```java
String exception
```

## isMirrored

This attribute stands for whether the barcode is mirrored.

```java
int isMirrored
```

## isDPM

This attribute stands for whether the barcode is recognized by DPM mode.

```java
int isMirrored
```
