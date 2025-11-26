---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Capture Vision Flutter
description: OneDCodeDetails class of DCV Flutter represents the extended info of a OneD Code.
keywords: oned code, details, result, barcode, extended
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# OneDCodeDetails

The `OneDCodeDetails` class encapsulates all of the extended details of a 1D Code that is not available in the regular barcode result, if the barcode is a 1D Code. 

> [!TIP]
> If you would like to learn more about the 1D format, please refer to the [barcode types](https://www.dynamsoft.com/barcode-reader/barcode-types/) page and go through the list of linear barcode symbologies.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class OneDCodeDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`startCharsBytes`](#startcharsbytes) | *Uint8List?* | A byte list representing the characters of the start pattern of a 1D barcode. |
| [`stopCharsBytes`](#stopcharsbytes) | *Uint8List?* | A byte list representing the characters of the stop pattern of a 1D barcode. |
| [`checkDigitBytes`](#checkdigitbytes) | *Uint8List?* | A byte list representing the check digit of the barcode, if applicable. |
| [`startPatternRange`](#startpatternrange) | *RangeValues* | Represents the position of the start pattern relative to the barcode location. |
| [`middlePatternRange`](#middlepatternrange) | *RangeValues* | Represents the position of the middle pattern relative to the barcode location. |
| [`endPatternRange`](#endpatternrange) | *RangeValues* | Represents the position of the end pattern relative to the barcode location. |

### startCharsBytes

A byte list representing the characters of the start pattern of a 1D barcode.

```dart
Uint8List? startCharsBytes;
```

**Remarks**

Each 1D barcode type has a unique start and stop pattern. These patterns are used to indicate the boundaries of the barcode which help the reader determine the direction to follow when reading the barcode.

### stopCharsBytes

A byte list representing the characters of the stop pattern of a 1D barcode.

```dart
Uint8List? stopCharsBytes;
```

**Remarks**

Each 1D barcode type has a unique start and stop pattern. These patterns are used to indicate the boundaries of the barcode which help the reader determine the direction to follow when reading the barcode.

### checkDigitBytes

A byte list representing the check digit of the barcode, if applicable.

```dart
Uint8List? checkDigitBytes;
```

**Remarks**

The check digit is a single digit that is concatenated at the end of a barcode's data in order to verify the accuracy of a scan. Different 1D barcodes have different ways to calculate the check digit.

### startPatternRange

Represents the position of the start pattern relative to the barcode location. The start pattern helps the reader determine the type of 1D barcode it's reading as well as determine the overall direction that the barcode should be read in.

```dart
RangeValues startPatternRange;
```

**Remarks**

The start of this range represents the x-coordinate of the start position as a percentage. The end of this range represents the x-coordinate of the end position as a percentage.

### middlePatternRange

Represents the position of the middle pattern relative to the barcode location. The middle, or center guard, pattern separates the two halves of the encoded data, and helps the Barcode Reader determine the reading direction while providing a fixed reference point for the reader.

```dart
RangeValues middlePatternRange;
```

**Remarks**

The start of this range represents the x-coordinate of the start position as a percentage. The end of this range represents the x-coordinate of the end position as a percentage.

### endPatternRange

Represents the position of the end pattern relative to the barcode location. The end pattern points to the end of the encoded data, with each barcode type having its own rules on where the end pattern appears.

```dart
RangeValues endPatternRange;
```

**Remarks**

The start of this range represents the x-coordinate of the start position as a percentage. The end of this range represents the x-coordinate of the end position as a percentage.

