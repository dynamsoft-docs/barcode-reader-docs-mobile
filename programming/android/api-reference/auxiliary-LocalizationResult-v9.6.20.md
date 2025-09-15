---
layout: default-layout
title: LocalizationResult Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the LocalizationResult Class of Dynamsoft Barcode Reader for Android SDK.
keywords: LocalizationResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/api-reference/auxiliary-LocalizationResult-v9.6.20.html
---

# LocalizationResult

The `LocalizationResult` extends the class [`TextResult`](auxiliary-TextResult.html) and [`IntermediateResult`](auxiliary-IntermediateResult.html). It stores the barcode localization data.

```java
class com.dynamsoft.dbr.LocalizationResult;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ----------- |
| [`terminatePhase`](#terminatephase) | *int* | The terminate phase of localization result. |
| [`barcodeFormat`](#barcodeformat) | *int* | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2 ) | *int* | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *String* | Barcode type as string. |
| [`resultPoints`](#resultpoints) | [`Point`](auxiliary-Point.html)\[\] | The vertices coordinates information of the barcode region. |
| [`angle`](#angle) | *int* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](#pagenumber) | *int* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](#regionname) | *String* | The region name the barcode located in. |
| [`documentName`](#documentname)| *String* | The document name. |
| [`resultCoordinateType`](#resultcoordinatetype) | *int* | The coordinate type. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *byte\[\]* | The accompanying text content in a byte array. |
| [`confidence`](#confidence) | *int* | The confidence of the localization result. |
| [`transformationMatrix`](#transformationmatrix) | *android.graphics.Matrix* | A transformation matrix that can transform the coordinates of the `resultPoints`. The `transformationMatrix` is calculated from the orientation information of the image. |

## terminatePhase

The terminate phase of localization result.

```java
int terminatePhase
```

**Value Range**

Any one of the [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=android) Enumeration items

**Default Value**

`TP_BARCODE_RECOGNIZED`

**Remarks**

When the recognition result is not desired, you can set this parameter can be set to skip certain processing stages.

**See Also**

[`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=android)

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

## resultPoints

The vertices coordinates information of the barcode region.

```java
Point[] resultPoints
```

**Related Class**

Class [`Point`](auxiliary-Point.html).

## angle

The angle of a barcode. Values range is from 0 to 360.

```java
int angle
```

## moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int moduleSize
```

## pageNumber

The page number the barcode located in. The index is 0-based. Only available when decoding files.

```java
int pageNumber
```

## regionName

The region name the barcode located in.

```java
String regionName
```

## documentName

The document name. Only available when decoding files.

```java
String documentName
```

## resultCoordinateType

The coordinate type.

```java
int resultCoordinateType
```

## accompanyingTextBytes

The accompanying text content in a byte array.

```java
byte[] accompanyingTextBytes
```

## confidence

The confidence of the localization result.

```java
int confidence
```

## transformationMatrix

A transformation matrix that can transform the coordinates of the `resultPoints`. The `transformationMatrix` is calculated from the orientation information of the image.

The images that captured by mobile cameras are always 90 degree counterclockwise rotated from what you see. The coordinates of `resultPoints` are based on the **image coordinate system**. You can use the `transformationMatrix` to rotate the resultPoints from the **image coordinate system** to the **real coordinate system**.

```java
android.graphics.Matrix transformationMatrix
```
