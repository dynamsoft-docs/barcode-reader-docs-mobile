---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: The OneDCodeDetails class of Dynamsoft Barcode Reader Android represents a barcode in OneD format. It inherits from the BarcodeDetails class and contains information about the start & stop char bytes, check digit bytes, and pattern ranges of the barcode.
keywords: OneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: OneDCodeDetails
permalink: /programming/android/api-reference/auxiliary-OneDCodeDetails.html
---

# OneDCodeDetails

`OneDCodeDetails` extends the [`BarcodeDetails`](barcode-details.md) class and represents detailed information specific to a 1D (one dimensional) barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class OneDCodeDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getStartCharsBytes`](#getstartcharsbytes) | Returns the start characters of the 1D barcode in a byte array. |
| [`getStopCharsBytes`](#getstopcharsbytes) | Returns the stop characters of the 1D barcode in a byte array. |
| [`getCheckDigitBytes`](#getcheckdigitbytes) | Returns the check digit characters of the 1D barcode in a byte array. |
| [`getStartPatternRange`](#getstartpatternrange) | Returns the position range of the start pattern relative to the barcode's location. |
| [`getMiddlePatternRange`](#getmiddlepatternrange) | Returns the position range of the middle pattern relative to the barcode's location. |
| [`getEndPatternRange`](#getendpatternrange) | Returns the position of the end pattern relative to the barcode location. |

### getStartCharsBytes

Returns the start characters of the 1D barcode in a byte array. Start characters are often used to identify the beginning of the barcode.

```java
byte[] getStartCharsBytes();
```

**Return Value**

A byte array representing the start characters of the 1D barcode.

### getStopCharsBytes

Returns the stop characters of the 1D barcode in a byte array. Stop characters are often used to identify the end of the barcode.

```java
byte[] getStopCharsBytes();
```

**Return Value**

A byte array representing the stop characters of the 1D barcode.

### getCheckDigitBytes

Returns the check digit characters of the 1D barcode in a byte array. Check digits are used for error detection and correction in some 1D barcodes.

```java
byte[] getCheckDigitBytes();
```

**Return Value**

A byte array representing the check digit characters of the 1D barcode.

### getStartPatternRange

Returns the position range of the start pattern relative to the barcode's location.

```java
Range<Float> getStartPatternRange();
```

**Return Value**

A `Range` of numbers representing the position range of the start pattern.

### getMiddlePatternRange

Returns the position range of the middle pattern relative to the barcode's location.


```java
Range<Float> getMiddlePatternRange();
```

**Return Value**

A `Range` of numbers representing the position range of the middle pattern.

### getEndPatternRange

Returns the position range of the end pattern relative to the barcode's location.

```java
Range<Float> getEndPatternRange();
```

**Return Value**

A `Range` of numbers representing the position range of the end pattern.
