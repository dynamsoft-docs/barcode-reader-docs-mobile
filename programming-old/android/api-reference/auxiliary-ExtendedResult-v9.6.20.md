---
layout: default-layout
title: ExtendedResult Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the ExtendedResult Class of Dynamsoft Barcode Reader for Android SDK.
keywords: ExtendedResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-ExtendedResult-v9.6.20.html
---


# ExtendedResult

`ExtendedResult` is the extension of the class [`TextResult`](auxiliary-TextResult.html). It stores the extended result information.

```java
class com.dynamsoft.dbr.ExtendedResult
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`resultType`](#resulttype) | *int* | Extended result type. |
| [`barcodeFormat`](#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *String* | Barcode type as a string. |
| [`confidence`](#confidence) | *int* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](#bytes) | *byte\[\]* | The content in a byte array. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *byte\[\]* | The accompanying text content in a byte array. |
| [`deformation`](#deformation) | *int* | The deformation value. |
| [`detailedResult`](#detailedresult) | *Object* | One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.html), [`PDF417Details`](auxiliary-PDF417Details.html), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.html), [`AztecDetails`](auxiliary-AztecDetails.html), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.html). |
| [`samplingImage`](#samplingimage) | [`SamplingImageData`](auxiliary-SamplingImageData.html) | The sampling image info. |
| [`clarity`](#clarity) | *int* | The clarity of the barcode zone in percentage. |

## resultType

Extended result type.

```java
int resultType
```

## barcodeFormat

Barcode type in BarcodeFormat group 1.

```java
int barcodeFormat
```

**Value Range**

One of the [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) Enumeration value.

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

## barcodeFormatString

Barcode type as string.

```java
String barcodeFormatString
```

**Value Range**

One of the barcode type in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) or [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android).

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

## confidence

The confidence of the result. The higher confidence means the higher accuracy. You can make the confidence filter throw the [`PublicRuntimeSettings.minResultConfidence`](auxiliary-PublicRuntimeSettings.html#minresultconfidence). The recommended minimum confidence value is 30.

```java
int confidence
```

## bytes

The content in a byte array.

```java
byte[] bytes
```

## accompanyingTextBytes

The accompanying text content in a byte array.

```java
byte[] accompanyingTextBytes
```

## deformation

The deformation value.

```java
int deformation
```

## detailedResult

One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.html), [`PDF417Details`](auxiliary-PDF417Details.html), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.html), [`AztecDetails`](auxiliary-AztecDetails.html), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.html).

```java
Object detailedResult
```

## samplingImage

The sampling image info.

```java
SamplingImageData samplingImage
```

## clarity

The clarity of the barcode zone in percentage.

```java
int clarity
```
