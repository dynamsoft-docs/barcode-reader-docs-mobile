---
layout: default-layout
title: DecodedBarcodeElement Class - Dynamsoft Barcode Reader Android Edition
description: DecodedBarcodeElement class of Dynamsoft Barcode Reader Android represents a decoded barcode element. It inherits from the RegionObjectElement class and provides additional functionality for retrieving information about the decoded barcode.
keywords: text, bytes, DecodedBarcodeElement, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DecodedBarcodeElement
---

# DecodedBarcodeElement Class

`DecodedBarcodeElement` extends the [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html) class and represents a decoded barcode element.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class DecodedBarcodeElement extends RegionObjectElement
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getText`](#gettext) | Returns the text of the decoded barcode. |
| [`setText`](#settext) | Set the text of the decoded barcode. |
| [`getBytes`](#getbytes) | Returns the raw bytes of the decoded barcode. |
| [`setBytes`](#setbytes) | Set the raw bytes of the decoded barcode. |
| [`isDPM`](#isdpm) | Specifies if the decoded barcode is a DPM code or not. |
| [`isMirrored`](#ismirrored) | Specifies if the decoded barcode is mirrored or not. |
| [`getFormat`](#getformat) | Returns the format of the decoded barcode. |
| [`setFormat`](#setformat) | Set the format of the decoded barcode. |
| [`getFormatString`](#getformatstring) | Returns the format of the decode barcode as a string. |
| [`getAngle`](#getangle) | Returns the orientation angle of the barcode. |
| [`getModuleSize`](#getmodulesize) | Returns the module size of the decoded barcode. |
| [`getConfidence`](#getconfidence) | Returns the confidence score of the decoded barcode. |
| [`setConfidence`](#setconfidence) | Set the confidence score of the barcode recognition result. |
| [`getDetails`](#getdetails) | Returns the `BarcodeDetails` of the decoded barcode. |
| [`getExtendedBarcodeResults`](#getextendedbarcoderesults) | Returns the extended barcode results of the decoded barcode. |
| [`setLocation`](#setlocation) | Sets the location of the decoded barcode. |

The following methods are inherited from [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### getText

Returns the text of the decoded barcode.

```java
String getText()
```

**Return Value**

A string representing the text of the decoded barcode.

### setText

Set the text of the decoded barcode. The barcode bytes are changed as well to reflect the new text.

```java
void setText(String text);
```

**Parameters**

`text`: The text to be set for the decoded barcode.

### getBytes

Returns the raw bytes of the decoded barcode.

```java
byte[] getBytes();
```

**Return Value**

A byte array representing the raw bytes of the decoded barcode.

### setBytes

Set the raw bytes of the decoded barcode. The text of the barcode will change to reflect the new barcode bytes.

```java
void setBytes(byte[] bytes);
```

**Parameters**

`bytes`: The raw bytes of the decoded barcode.

### isDPM

Specifies if the decoded barcode is a Direct Part Marking (DPM) code or not. DPM codes are read by setting the [`DPMCodeReadingModes`]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/dpm-code-reading-modes.html).

```java
boolean isDPM();
```

**Return Value**

A `BOOL` value describing whether the barcode is a DPM code or not.

### isMirrored

Specifies if the decoded barcode is mirrored or not. Mirrored barcodes are read by setting the [`MirrorMode`]({{site.dcvb_parameters_reference}}barcode-format-specification/mirror-mode.html).

```java
boolean isMirrored();
```

**Return Value**

A `BOOL` value describing whether the barcode is mirrored or not.

### getFormat

Returns the format of the decoded barcode as a [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) item.

```java
EnumBarcodeFormat getFormat();
```

**Return Value**

A [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) item representing the format of the decoded barcode.

### setFormat

Sets the format of the decoded barcode as a [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) item.

```java
void setFormat(@EnumBarcodeFormat long format);
```

**Parameters**

`format`: The [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) of the decoded barcode.

### getFormatString

Returns the format of the decode barcode as a string.

```java
String getFormatString();
```

**Return Value**

A string representing the format of the barcode.

### getAngle

Returns the orientation angle of the decoded barcode should it be rotated in any way.

```java
int getAngle();
```

**Return Value**

An integer representing the orientation angle of the barcode.

### getModuleSize

Returns the module size of the decoded barcode.

```java
int getModuleSize();
```

**Return Value**

An integer representing the module size of the decoded barcode.

### getConfidence

Returns the confidence score of the decoded barcode.

```java
int getConfidence();
```

**Return Value**

An integer representing the confidence score.

### setConfidence

Sets the confidence score of the decoded barcode.

```java
void setConfidence(int confidence);
```

**Parameters**

`confidence`: The confidence score of the barcode recognition result.

### getDetails

Returns the [`BarcodeDetails`](barcode-details.md) of the decoded barcode.

```java
BarcodeDetails getDetails();
```

**Return Value**

A [`BarcodeDetails`](barcode-details.md) object representing the details of the decoded barcode.

### getExtendedBarcodeResults

Returns the extended barcode result(s) of the decoded barcode as a [`ExtendedBarcodeResult`](auxiliary-ExtendedResult.md) object. Please visit the `ExtendedBarcodeResult` page to learn more of what information is contained there.

```java
ExtendedBarcodeResult[] getExtendedBarcodeResults();
```

**Return Value**

An array of [`ExtendedBarcodeResult`](auxiliary-ExtendedResult.md) that represents the extended barcode results.

### setLocation

Sets the location of the decoded barcode.

```java
int setLocation(Quadrilateral location);
```

**Parameters**

`location`: The location of the decoded barcode as a [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html) object.

**Return Value**

Returns 0 if it succeeds. Otherwise, returns an error code.
