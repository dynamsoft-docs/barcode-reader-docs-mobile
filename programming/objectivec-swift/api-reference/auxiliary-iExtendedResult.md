---
layout: default-layout
title: DSExtendedBarcodeResult Class - Dynamsoft Barcode Reader iOS Edition
description: DSExtendedBarcodeResult class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: DSExtendedBarcodeResult, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSExtendedBarcodeResult
permalink: /programming/objectivec-swift/api-reference/auxiliary-ExtendedResult.html
---


# DSExtendedBarcodeResult

The `DSExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

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
| [`detailedResult`](#detailedresult) | *Object* | One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.md), [`PDF417Details`](auxiliary-PDF417Details.md), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md), [`AztecDetails`](auxiliary-AztecDetails.md), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.md). |
| [`samplingImage`](#samplingimage) | [`SamplingImageData`](auxiliary-SamplingImageData.md) | The sampling image info. |
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

One of the [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc&swift) Enumeration value.

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc&swift), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc&swift)

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

```java
int barcodeFormat_2
```

**Value Range**

One of the [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc&swift) Enumeration items

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc&swift), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc&swift)

## barcodeFormatString

Barcode type as string.

```java
String barcodeFormatString
```

**Value Range**

One of the barcode type in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc&swift) or [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc&swift).

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc&swift), [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc&swift)

## confidence

The confidence of the result. The higher confidence means the higher accuracy. You can make the confidence filter throw the [`PublicRuntimeSettings.minResultConfidence`](auxiliary-PublicRuntimeSettings.md#minresultconfidence). The recommended minimum confidence value is 30.

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

One of the following: [`QRCodeDetails`](auxiliary-QRCodeDetails.md), [`PDF417Details`](auxiliary-PDF417Details.md), [`DataMatrixDetails`](auxiliary-DataMatrixDetails.md), [`AztecDetails`](auxiliary-AztecDetails.md), [`OneDCodeDetails`](auxiliary-OneDCodeDetails.md).

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
