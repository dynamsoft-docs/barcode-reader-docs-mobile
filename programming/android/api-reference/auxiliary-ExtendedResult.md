---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader Android Edition
description: ExtendedBarcodeResult class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: ExtendedBarcodeResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ExtendedBarcodeResult
permalink: /programming/android/api-reference/auxiliary-ExtendedResult.html
---


# ExtendedBarcodeResult

The `ExtendedBarcodeResult` class represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ExtendedBarcodeResult extends DecodedBarcodeElement
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Get the type of the extended barcode result. |
| [`getDeformation`](#getdeformation) | Get the deformation level of the barcode zone. |
| [`getClarity`](#getclarity) | Get the clarity level of the barcode zone. |
| [`getSamplingImage`](#getsamplingimage) | Get the sampling image of the barcode zone. |

## Inherited Methods

The following methods are inherited from class [`DecodedBarcodeElement`](decoded-barcode-element.md).

| Method | Description |
| ------ | ----------- |
| [`getText`](decoded-barcode-element.md#gettext) | Get the text of the decoded barcode.|
| [`getBytes`](decoded-barcode-element.md#getbytes) | Get the raw bytes of the decoded barcode.|
| [`isDPM`](decoded-barcode-element.md#isdpm) | Check whether the barcode is a DPM (Direct Part Marking) barcode (decoded by DPMReadingMode).|
| [`isMirrored`](decoded-barcode-element.md#ismirrored) | Check whether the barcode is mirrored (decoded by MirrorMode).|
| [`getFormat`](decoded-barcode-element.md#getformat) | Get the format of the decoded barcode as a barcode format enumeration.|
| [`getFormatString`](decoded-barcode-element.md#getformatstring) | Get the format of the decode barcode as a string.|
| [`getAngle`](decoded-barcode-element.md#getangle) | The orientation angle of the barcode.|
| [`getModuleSize`](decoded-barcode-element.md#getmodulesize) | Get the module size of the decoded barcode.|
| [`getConfidence`](decoded-barcode-element.md#getconfidence) | Get the confidence score of the barcode recognition result.|
| [`getDetails`](decoded-barcode-element.md#getdetails) | Get the details of the decoded barcode.|
| [`getExtendedBarcodeResults`](decoded-barcode-element.md#getextendedbarcoderesults) | Get an array of extended barcode results.|

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

| Method | Description |
| ------ | ----------- |
| [`getLocation`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getlocation) | Gets the location info of the element that defined in Quadrilateral. |
| [`getReferencedElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getreferencedelement) | Gets the referenced element that supports the capturing of this element. |
| [`getRegionObjectElementType`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html#getregionobjectelementtype) | Gets the type of the element. |

### getExtendedBarcodeResultType

Get the type of the extended barcode result.

```java
EnumExtendedBarcodeResultType getExtendedBarcodeResultType();
```

**Return Value**

The type of the extended barcode result.

### getDeformation

Get the deformation level of the barcode zone.

```java
int getDeformation();
```

**Return Value**

The deformation level of the barcode zone.

### getClarity

Get the clarity level of the barcode zone.

```java
int getClarity();
```

**Return Value**

The clarity level of the barcode zone.

### getSamplingImage

Get the sampling image of the barcode zone.

```java
ImageData getSamplingImage();
```

**Return Value**

An ImageData object as the sampling image of the barcode zone.
