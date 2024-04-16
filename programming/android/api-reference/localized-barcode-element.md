---
layout: default-layout
title: LocalizedBarcodeElement Class - Dynamsoft Barcode Reader Android Edition
description: The LocalizedBarcodeElement class represents a localized barcode element detected in an image. It is inherited from RegionObjectElement class.
keywords: GetAngle, GetConfidence, GetFormat, GetFormatString, GetModuleSize, LocalizedBarcodeElement, api reference
permalink: /programming/android/api-reference/localized-barcode-element.html
---

# LocalizedBarcodeElement Class

The `LocalizedBarcodeElement` class represents a localized barcode element detected in an image. It is inherited from [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr.intermediate_results

```java
class LocalizedBarcodeElement extends RegionObjectElement
```

## Methods

| Method | Description |
|--------|-------------|
| [`getAngle`](#getangle) | Gets the orientation angle of the barcode. |
| [`getConfidence`](#getconfidence) | Gets the confidence score of the barcode localization result. |
| [`getPossibleFormats`](#getpossibleformats) | Gets the possible format of the barcode. |
| [`setPossibleFormats`](#setpossibleformats) | Sets the possible format of the barcode. |
| [`getPossibleFormatsString`](#getpossibleformatsstring) | Get all possible formats of the localized barcode in one string splited by ",". |
| [`getModuleSize`](#getmodulesize) | Gets the module size of the barcode. |

## Inherited Methods

The following methods are inherited from class [`RegionObjectElement`]({{ site.dcv_android_api }}core/intermediate-results/region-object-element.html).

{%- include api-reference/region-object-element-android.md -%}

### getAngle

Get the orientation angle of the barcode.

```java
int getAngle();
```

**Return value**

Returns the orientation angle of the barcode.

### getConfidence

Get the confidence score of the barcode localization result.

```java
int getModuleSize();
```

**Return value**

Returns the confidence score of the barcode recognition result. It represents the confidence that the positioning area is a barcode.

### getPossibleFormats

Get the format of the barcode.

```java
long getPossibleFormats();
```

**Return value**

Returns the format of the barcode.

**See Also**

[Enumeration BarcodeFormat]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=android)

### setPossibleFormats

Set the possibleformat of the barcode.

```java
void setPossibleFormats(long possibleFormats);
```

**Parameters**

`possibleFormats`: The format of the barcode.

### getPossibleFormatsString

Get all possible formats of the localized barcode in one string splited by ",".

```java
String getPossibleFormatsString();
```

**Return value**

Returns the string representation of the barcode format in one string splited by ",".

### getModuleSize

Get the module size of the barcode.

```java
int getModuleSize();
```

**Return value**

Returns the module size of the barcode.
