---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Android Edition
description: BarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from CapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
permalink: /programming/android/api-reference/barcode-result-item.html
---

# BarcodeResultItem Class

`BarcodeResultItem` extends the [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html) class and represents a single barcode result. This is the most basic item of the decoded barcode result, one of the captured result types that the Capture Vision Router can output.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class BarcodeResultItem extends CapturedResultItem
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getFormat`](#getformat) | Returns the format of the barcode. |
| [`getFormatString`](#getformatstring) | Returns the format text of the barcode. |
| [`getText`](#gettext) | Returns the decode text of the barcode. |
| [`getBytes`](#getbytes) | Returns the decode byte of the barcode. |
| [`getLocation`](#getlocation) | Returns the location of the barcode. |
| [`getConfidence`](#getconfidence) | Returns the confidence of the decoding result. |
| [`getAngle`](#getangle) | Returns the rotation angle of the barcode. |
| [`getModuleSize`](#getmodulesize) | Returns the module size of the barcode. |
| [`getDetails`](#getdetails) | Returns the details of the decoded barcode. |
| [`isDPM`](#isdpm) | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](#ismirrored) | Specifies if the decoded barcode is mirrored or not. |

## Inherited Methods

The following methods are inherited from [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

| Method | Description |
| ------ | ----------- |
| [`getType`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettype) | Returns the type of the captured result item. |
| [`getReferencedItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#getreferenceditem) | Returns the referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |

### getFormat

Returns the format of the barcode. This format will be one of the [`EnumBarcodeFormat`]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=android) items.

```java
long getFormat()
```

**Return Value**

The [`EnumBarcodeFormat`]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=android) of the barcode.

### getFormatString

Returns the format of the barcode, but as a string instead of a `BarcodeFormat` enumeration item. 

```java
String getFormatString()
```

**Return Value**

The format text of the barcode.

### getText

Returns the raw decoded text of the barcode.

```java
String getText()
```

**Return Value**

The raw decoded text of the barcode.

### getBytes

Returns the raw bytes of the decoded barcode text which is useful when the text string cannot be used.

```java
byte[] getBytes()
```

**Return Value**

The bytes of the decoded barcode.

### getLocation

Returns the location of the barcode as a [`Quadrilateral`]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html). The quadrilateral contains the four vertices of the location, with the first vertex in the `points` array being the top-left most vertex, and then going in a clockwise direction.

```java
Quadrilateral getLocation()
```

**Return Value**

A `Quadrilateral` object representing the location of the barcode.

### getConfidence

Returns the confidence of the decoded result, which is a measure of the result's accuracy or reliability. If the confidence is lower than 30, the result will not be output by default. To change the minimum accepted confidence score for a barcode, please see the [`minResultConfidence`](simplified-barcode-reader-settings.md#minresultconfidence) setting.

```java
int getConfidence()
```

**Return Value**

An integer representing the confidence of the barcode result.

### getAngle

If the barcode is captured at an angle or is rotated by any measure, this method returns the rotation angle of the barcode.

```java
int getAngle()
```

**Return Value**

An integer representing the rotation angle of the barcode.

### getModuleSize

Returns the size of the individual modules or elements within the barcode.

```java
int getModuleSize()
```

**Return Value**

An integer representing the module size of the barcode.

### getDetails

Returns the details of the decoded barcode. [BarcodeDetails](barcode-details.md) can offer much more enhanced details specific to the barcode format of the decoded barcode. If you would like to learn more about how you can use these barcode details, please see this article on [how to get detailed barcode info]({{site.features}}get-detailed-info.html?lang=android).

```java
BarcodeDetails getDetails()
```

**Return Value**

A `BarcodeDetails` object representing the details of the decoded barcode.

### isDPM

Specifies if the decoded barcode is a Direct Part Marking (DPM) code or not. To learn how to read DPM codes, please visit [how to read DPM codes]({{site.usecases}}read-dpm-codes.html?lang=android).

```java
boolean isDPM()
```

**Return Value**

A `BOOL` value describing whether the barcode is a DPM code or not.

### isMirrored

Specifies if the decoded barcode is mirrored or not. Mirrored barcodes are read by setting the [`MirrorMode`]({{site.dcv_parameters_reference}}barcode-format-specification/mirror-mode.html).

```java
boolean isMirrored()
```

**Return Value**

A `BOOL` value describing whether the barcode is mirrored or not.
