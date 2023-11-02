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

The `BarcodeResultItem` class represents a barcode result item decoded by the barcode reader. It is derived from [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class BarcodeResultItem extends CapturedResultItem
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getFormat`](#getformat) | Get the format of the barcode. |
| [`getFormatString`](#getformatstring) | Get the format text of the barcode. |
| [`getText`](#gettext) | Get the decode text of the barcode. |
| [`getBytes`](#getbytes) | Get the decode byte of the barcode. |
| [`getLocation`](#getlocation) | Get the location of the barcode. |
| [`getConfidence`](#getconfidence) | Get the confidence of the decoding result. |
| [`getAngle`](#getangle) | Get the rotation angle of the barcode. |
| [`getModuleSize`](#getmodulesize) | Get the module size of the barcode. |
| [`getDetails`](#getdetails) | Get the details of the decoded barcode. |
| [`isDPM`](#isdpm) | Check whether the barcode is a DPM barcode. |
| [`isMirrored`](#ismirrored) | Check whether the barcode is mirrored. |

## Inherited Methods

The following methods are inherited from class [`CapturedResultItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html).

| Method | Description |
| ------ | ----------- |
| [`getType`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#gettype) | Get the type of the captured result item. |
| [`getReferencedItem`]({{ site.dcv_android_api }}core/basic-structures/captured-result-item.html#getreferenceditem) | Get the referenced captured result item. The reference dependencies is defined in the Capture Vision settings. |

### getFormat

Get the format of the barcode. This format will be one of the [`EnumBarcodeFormat`]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=android) items.

```java
long getFormat()
```

**Return Value**

The format of the barcode.

### getFormatString

Get the format of the barcode, but as text instead of a `BarcodeFormat` item. 

```java
String getFormatString()
```

**Return Value**

The format text of the barcode.

### getText

Get the raw decoded text of the barcode.

```java
String getText()
```

**Return Value**

The raw decoded text of the barcode.

### getBytes

Get the raw bytes of the decoded barcode text.

```java
byte[] getBytes()
```

**Return Value**

The decode byte of the barcode.

### getLocation

Get the location of the barcode as a [DSQuadrilateral]({{ site.dcv_android_api }}core/basic-structures/quadrilateral.html). The quadrilateral contains the four vertex points of the location, with the first vertex being the left-most vertex, and going in a clockwise direction.

```java
Quadrilateral getLocation()
```

**Return Value**

The location of the barcode.

### getConfidence

Get the confidence of the decoded result, which is a measure of the result's accuracy. If the confidence is lower than 30, the result will not be output by default.

```java
int getConfidence()
```

**Return Value**

The confidence of the decoding result.

### getAngle

If the barcode is captured at an angle, this method returns the rotation angle of the barcode.

```java
int getAngle()
```

**Return Value**

The rotation angle of the barcode.

### getModuleSize

Get the module size of the barcode. If the module size of the barcodes are consistently small, please see this article on how to [read barcodes with small module sizes]({{site.features}}read-barcodes-with-small-module-size.html?lang=android).

```java
int getModuleSize()
```

**Return Value**

The module size of the barcode.

### getDetails

Gets the details of the decoded barcode. [DSBarcodeDetails](barcode-details.md) can offer much more enhanced details specific to the barcode format of the decoded barcode. If you would like to learn more about how you can use these barcode details, please see this article on [how to get detauled barcode info]({{site.features}}get-detailed-info.html?lang=android).

```java
BarcodeDetails getDetails()
```

**Return Value**

The details of the decoded barcode.

### isDPM

Tells you whether the barcode is a DPM barcode, which is a unique type of Datamatrix code. Please visit this page if you would like to learn more on [how to read DPM codes]({{site.usecases}}read-dpm-codes.html?lang=android).

```java
boolean isDPM()
```

**Return Value**

If true, the barcode is a DPM barcode. Otherwise, the barcode isn't a DPM barcode.

### isMirrored

Check whether the barcode is mirrored.

```java
boolean isMirrored()
```

**Return Value**

If true, the barcode is mirrored. Otherwise, the barcode isn't mirrored.
