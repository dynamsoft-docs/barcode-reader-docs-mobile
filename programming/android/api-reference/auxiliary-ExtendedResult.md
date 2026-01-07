---
layout: default-layout
title: ExtendedBarcodeResult Class - Dynamsoft Barcode Reader Android Edition
description: ExtendedBarcodeResult class of Dynamsoft Barcode Reader Android represents an extended barcode result in a decoded barcode element. It contains information such as the type of extended barcode, deformation, clarity, and a sampling image of the barcode.
keywords: ExtendedBarcodeResult, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: ExtendedBarcodeResult
permalink: /programming/android/api-reference/auxiliary-ExtendedResult.html
---


# ExtendedBarcodeResult

`ExtendedBarcodeResult` extends the [`DecodedBarcodeElement`](decoded-barcode-element.md) class and represents extended information about a barcode result.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class ExtendedBarcodeResult extends DecodedBarcodeElement
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getExtendedBarcodeResultType`](#getextendedbarcoderesulttype) | Returns the type of the extended barcode result. |
| [`getDeformation`](#getdeformation) | Returns the deformation level of the barcode zone. |
| [`getClarity`](#getclarity) | Returns the clarity score of the barcode zone. |
| [`getSamplingImage`](#getsamplingimage) | Returns the sampling image of the barcode zone. |

The following methods are inherited from class [`DecodedBarcodeElement`](decoded-barcode-element.md).

| Method | Description |
| ------ | ----------- |
| [`getText`](decoded-barcode-element.md#gettext) | Returns the text of the decoded barcode. |
| [`setText`](decoded-barcode-element.md#settext) | Set the text of the decoded barcode. |
| [`getBytes`](decoded-barcode-element.md#getbytes) | Returns the raw bytes of the decoded barcode. |
| [`setBytes`](decoded-barcode-element.md#setbytes) | Set the raw bytes of the decoded barcode. |
| [`isDPM`](decoded-barcode-element.md#isdpm) | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](decoded-barcode-element.md#ismirrored) | Specifies if the decoded barcode is mirrored or not. |
| [`getFormat`](decoded-barcode-element.md#getformat) | Returns the format of the decoded barcode. |
| [`setFormat`](decoded-barcode-element.md#setformat) | Set the format of the decoded barcode. |
| [`getFormatString`](decoded-barcode-element.md#getformatstring) | Returns the format of the decode barcode as a string. |
| [`getAngle`](decoded-barcode-element.md#getangle) | Returns the orientation angle of the barcode. |
| [`getModuleSize`](decoded-barcode-element.md#getmodulesize) | Returns the module size of the decoded barcode. |
| [`getConfidence`](decoded-barcode-element.md#getconfidence) | Returns the confidence score of the decoded barcode. |
| [`setConfidence`](decoded-barcode-element.md#setconfidence) | Set the confidence score of the barcode recognition result. |
| [`getDetails`](decoded-barcode-element.md#getdetails) | Returns the `BarcodeDetails` of the decoded barcode. |
| [`getExtendedBarcodeResults`](decoded-barcode-element.md#getextendedbarcoderesults) | Returns the extended barcode results of the decoded barcode. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html).

| Method | Description |
| ------ | ----------- |
| [`getLocation`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html#getlocation) | Gets the location of the region object, represented as a [`Quadrilateral`](../basic-structures/quadrilateral.md). |
| [`setLocation`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html#setlocation) | Sets the location of the region object, represented as a [`Quadrilateral`](../basic-structures/quadrilateral.md). |
| [`getReferencedElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html#getreferencedelement) | Gets the referenced element that supports the capturing of this element. |
| [`getRegionObjectElementType`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html#getregionobjectelementtype) | The type of the region object element, defined by the enumeration `EnumRegionObjectElementType`. |

### getExtendedBarcodeResultType

Returns the type of the extended barcode result as a [`ExtendedBarcodeResultType`]({{ site.dbr_android_api }}enum/extended-barcode-result-type.html?lang=android) enumeration item.

```java
@EnumExtendedBarcodeResultType
int getExtendedBarcodeResultType();
```

**Return Value**

A [`EnumExtendedBarcodeResultType`]({{ site.dbr_android_api }}enum/extended-barcode-result-type.html?lang=android) item representing the extended barcode result type.

### getDeformation

Returns the degree of deformation or distortion of the decoded barcode.

```java
int getDeformation();
```

**Return Value**

An integer representing the deformation level of the barcode zone.

### getClarity

Returns the clarity/quality level of the decoded barcode.

```java
int getClarity();
```

**Return Value**

An integer representing the clarity/quality level of the barcode zone.

### getSamplingImage

Returns the sampling image of the decoded barcode as a [`ImageData`]({{ site.dcvb_android_api }}core/basic-structures/image-data.html) object.

```java
ImageData getSamplingImage();
```

**Return Value**

An `ImageData` object representing the sampling image of the barcode zone.
