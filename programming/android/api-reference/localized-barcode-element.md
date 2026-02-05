---
layout: default-layout
title: LocalizedBarcodeElement Class - Dynamsoft Barcode Reader Android Edition
description: The LocalizedBarcodeElement class of Dynamsoft Barcode Reader Android represents a localized barcode element detected in an image. It is inherited from RegionObjectElement class.
keywords: GetAngle, GetConfidence, GetFormat, GetFormatString, GetModuleSize, LocalizedBarcodeElement, api reference
---

# LocalizedBarcodeElement Class

`LocalizedBarcodeElement` extends the [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html) class and represents a localized barcode element detected in an image.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class LocalizedBarcodeElement extends RegionObjectElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`getAngle`](#getangle) | Returns the orientation angle of the localized barcode. |
| [`getConfidence`](#getconfidence) | Returns the confidence score of the localized barcode. |
| [`getPossibleFormats`](#getpossibleformats) | Returns the possible formats of the localized barcode. |
| [`setPossibleFormats`](#setpossibleformats) | Sets the possible format of the localized barcode. |
| [`getPossibleFormatsString`](#getpossibleformatsstring) | Returns the possible formats of the localized barcode as a string. |
| [`getModuleSize`](#getmodulesize) | Returns the module size of the localized barcode. |
| [`setLocation`](#setlocation) | Sets the location of the localized barcode. |

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### getAngle

Returns the orientation angle of the localized barcode element, indicating how the element is positioned or rotated within the barcode.

```java
int getAngle();
```

**Return value**

An integer representing the orientation angle of the localized barcode.

### getConfidence

Returns the confidence/reliability score of the localization of the barcode element.

```java
int getConfidence();
```

**Return value**

An integer representing the confidence score of the localized barcode element, which represents the confidence that the positioning area is a barcode.

### getPossibleFormats

Returns the possible formats of the localized barcode since the barcode has not been decoded yet, so the exact format is not yet determined.

```java
long getPossibleFormats();
```

**Return value**

Returns the possible format(s) of the localized barcode.

**See Also**

[EnumBarcodeFormat]({{ site.dbr_android_api }}enum/barcode-format.html?lang=android)

### setPossibleFormats

Set the possibleformat of the barcode.

```java
void setPossibleFormats(@EnumBarcodeFormat long possibleFormats);
```

**Parameters**

`possibleFormats`: The format of the barcode.

### getPossibleFormatsString

Returns the possible format(s) of the localized barcode as a string, with each format split by a comma (","). Since the barcode has not been decoded yet, the exact format is not yet determined.

```java
String getPossibleFormatsString();
```

**Return value**

A string representing all the possible formats of the localized barcode.

### getModuleSize

Returns the size of the individual modules within the localized barcode element.

```java
int getModuleSize();
```

**Return value**

An integer representing the module size of the localized barcode.

### setLocation

Sets the location of the localized barcode.

```java
int setLocation(Quadrilateral location)
```

**Parameters**

`location`: The location of the localized barcode, represented as a [`Quadrilateral`]({{ site.dcvb_android_api }}core/basic-structures/quadrilateral.html).

**Return value**

Returns 0 if the location is set successfully, otherwise returns the error code.
