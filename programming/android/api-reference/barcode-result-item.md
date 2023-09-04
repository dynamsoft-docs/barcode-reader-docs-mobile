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

The `BarcodeResultItem` class represents a barcode result item decoded by barcode reader engine. It is derived from `CapturedResultItem`.

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

### getFormat

Get the format of the barcode.

```java
long getFormat()
```

**Return Value**

The format of the barcode.

### getFormatString

Get the format text of the barcode.

```java
String getFormatString()
```

**Return Value**

The format text of the barcode.

### getText

Get the decode text of the barcode.

```java
String getText()
```

**Return Value**

The decode text of the barcode.

### getBytes

Get the decode byte of the barcode.

```java
byte[] getBytes()
```

**Return Value**

The decode byte of the barcode.

### getLocation

Get the location of the barcode.

```java
Quadrilateral getLocation()
```

**Return Value**

The location of the barcode.

### getConfidence

Get the confidence of the decoding result.

```java
int getConfidence()
```

**Return Value**

The confidence of the decoding result.

### getAngle

Get the rotation angle of the barcode.

```java
int getAngle()
```

**Return Value**

The rotation angle of the barcode.

### getModuleSize

Get the module size of the barcode.

```java
int getModuleSize()
```

**Return Value**

The module size of the barcode.

### getDetails

Get the details of the decoded barcode.

```java
BarcodeDetails getDetails()
```

**Return Value**

The details of the decoded barcode.

### isDPM

Check whether the barcode is a DPM barcode.

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
