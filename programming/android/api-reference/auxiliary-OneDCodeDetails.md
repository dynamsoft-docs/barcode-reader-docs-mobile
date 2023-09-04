---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: The OneDCodeDetails class represents a barcode in OneD format. It inherits from the BarcodeDetails class and contains information about the start & stop char bytes, check digit bytes, and pattern ranges of the barcode.
keywords: OneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: OneDCodeDetails
permalink: /programming/android/api-reference/auxiliary-OneDCodeDetails.html
---

# OneDCodeDetails

`OneDCodeDetails` class represents detailed information about a one-dimensional barcode. It inherits from the [`BarcodeDetails`](barcode-details.md) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class OneDCodeDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`OneDCodeDetails`](#onedcodedetails-1) | The constructor. Initializes a new instance of the OneDCodeDetails class. |
| [`getStartCharsBytes`](#getstartcharsbytes) | The start chars of the one-dimensional barcode in a byte array. |
| [`getStopCharsBytes`](#getstopcharsbytes) | The stop chars of the one-dimensional barcode in a byte array. |
| [`getCheckDigitBytes`](#getcheckdigitbytes) | The check digit chars of the one-dimensional barcode in a byte array. |
| [`getStartPatternRange`](#getstartpatternrange) | The position of the start pattern relative to the barcode location. |
| [`getMiddlePatternRange`](#getmiddlepatternrange) | The position of the middle pattern relative to the barcode location. |
| [`getEndPatternRange`](#getendpatternrange) | The position of the end pattern relative to the barcode location. |

### OneDCodeDetails

The constructor. Initializes a new instance of the `OneDCodeDetails` class.

```java
OneDCodeDetails();
```

### getStartCharsBytes

The start chars of the one-dimensional barcode in a byte array.

```java
byte[] getStartCharsBytes();
```

**Return Value**

The start chars of the one-dimensional barcode in a byte array.

### getStopCharsBytes

The stop chars of the one-dimensional barcode in a byte array.

```java
byte[] getStopCharsBytes();
```

**Return Value**

The stop chars of the one-dimensional barcode in a byte array.

### getCheckDigitBytes

The check digit chars of the one-dimensional barcode in a byte array.

```java
byte[] getCheckDigitBytes();
```

**Return Value**

The check digit chars of the one-dimensional barcode in a byte array.

### getStartPatternRange

The position of the start pattern relative to the barcode location.

```java
Range<Float> getStartPatternRange();
```

**Return Value**

The position of the start pattern relative to the barcode location.

### getMiddlePatternRange

The position of the middle pattern relative to the barcode location.

```java
Range<Float> getMiddlePatternRange();
```

**Return Value**

The position of the middle pattern relative to the barcode location.

### getEndPatternRange

The position of the end pattern relative to the barcode location.

```java
Range<Float> getEndPatternRange();
```

**Return Value**

The position of the end pattern relative to the barcode location.
