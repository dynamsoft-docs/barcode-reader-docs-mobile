---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodeElement class represents a decoded barcode element. It inherits from the RegionObjectElement class and provides additional functionality for retrieving information about the decoded barcode.
keywords: text, bytes, DecodedBarcodeElement, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodeElement
permalink: /programming/android/api-reference/decoded-barcode-element-v10.0.21.html
---

# DecodedBarcodeElement Class

The `DecodedBarcodeElement` class represents a decoded barcode element. It inherits from the [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html) class class and provides additional functionality for retrieving information about the decoded barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DecodedBarcodeElement
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getText`](#gettext) | Get the text of the decoded barcode.|
| [`getBytes`](#getbytes) | Get the raw bytes of the decoded barcode.|
| [`isDPM`](#isdpm) | Check whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode).|
| [`isMirrored`](#ismirrored) | Check whether the barcode is mirrored (decoded by MirrorMode).|
| [`getFormat`](#getformat) | Get the format of the decoded barcode as a barcode format enumeration.|
| [`getFormatString`](#getformatstring) | Get the format of the decode barcode as a string.|
| [`getAngle`](#getangle) | The orientation angle of the barcode.|
| [`getModuleSize`](#getmodulesize) | Get the module size of the decoded barcode.|
| [`getConfidence`](#getconfidence) | Get the confidence score of the barcode recognition result.|
| [`getDetails`](#getdetails) | Get the details of the decoded barcode.|
| [`getExtendedBarcodeResults`](#getextendedbarcoderesults) | Get an array of extended barcode results.|

## Inherited Methods

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

| Method | Description |
| ------ | ----------- |
| [`getLocation`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getlocation) | Gets the location info of the element that defined in Quadrilateral. |
| [`getReferencedElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getreferencedelement) | Gets the referenced element that supports the capturing of this element. |
| [`getRegionObjectElementType`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getregionobjectelementtype) | Gets the type of the element. |

### getText

Get the text of the decoded barcode.

```java
String getText()
```

**Return Value**

The text of the decoded barcode.

### getBytes

Get the raw bytes of the decoded barcode.

```java
byte[] getBytes();
```

**Return Value**

The raw bytes of the decoded barcode.

### isDPM

Check whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode).

```java
boolean isDPM();
```

**Return Value**

If true, the barcode is a DPM barcode. Otherwise, the barcode isn't a DPM barcode.

### isMirrored

Check whether the barcode is mirrored (decoded by MirrorMode).

```java
boolean isMirrored();
```

**Return Value**

If true, the barcode is mirrored. Otherwise, the barcode isn't mirrored.

### getFormat

Get the format of the decoded barcode as a barcode format enumeration.

```java
long getFormat();
```

**Return Value**

The format of the decoded barcode as a barcode format enumeration.

### getFormatString

Get the format of the decode barcode as a string.

```java
String getFormatString();
```

**Return Value**

The format of the decode barcode as a string.

### getAngle

Get the orientation angle of the barcode.

```java
int getAngle();
```

**Return Value**

The orientation angle of the barcode.

### getModuleSize

Get the module size of the decoded barcode.

```java
int getModuleSize();
```

**Return Value**

The module size of the decoded barcode.

### getConfidence

Get the confidence score of the barcode recognition result.

```java
int getConfidence();
```

**Return Value**

The confidence score of the barcode recognition result.

### getDetails

Get the details of the decoded barcode.

```java
BarcodeDetails getDetails();
```

**Return Value**

The details of the decoded barcode.

### getExtendedBarcodeResults

Get an array of extended barcode results.

```java
ExtendedBarcodeResult[] getExtendedBarcodeResults();
```

**Return Value**

The array that represent the extended barcode results.
