---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Capture Vision React Native
description: OneDCodeDetails class of DCV React Native represents the extended info of a OneD Code.
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

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
interface OneDCodeDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`startCharsBytes`](#startcharsbytes) | *number[]* | A byte list representing the characters of the start pattern of a 1D barcode. |
| [`stopCharsBytes`](#stopcharsbytes) | *number[]* | A byte list representing the characters of the stop pattern of a 1D barcode. |
| [`checkDigitBytes`](#checkdigitbytes) | *number[]* | A byte list representing the check digit of the barcode, if applicable. |
| [`startPatternRange_lower`](#startpatternrange_lower) | *number* | The lower bound of the start pattern range. Represents the position of the start pattern relative to the barcode location. |
| [`startPatternRange_upper`](#startpatternrange_upper) | *number* | The upper bound of the start pattern range. Represents the position of the start pattern relative to the barcode location. |
| [`middlePatternRange_lower`](#middlepatternrange_lower) | *number* | The lower bound of the middle pattern range. Represents the position of the middle pattern relative to the barcode location. |
| [`middlePatternRange_upper`](#middlepatternrange_upper) | *number* | The upper bound of the middle pattern range. Represents the position of the middle pattern relative to the barcode location. |
| [`endPatternRange_lower`](#endpatternrange_lower) | *number* | The lower bound of the end pattern range. Represents the position of the end pattern relative to the barcode location. |
| [`endPatternRange_upper`](#endpatternrange_upper) | *number* | The upper bound of the end pattern range. Represents the position of the end pattern relative to the barcode location. |


### startCharsBytes

A byte list representing the characters of the start pattern of a 1D barcode.

```tsx
startCharsBytes: number[];
```

**Remarks**

Each 1D barcode type has a unique start and stop pattern. These patterns are used to indicate the boundaries of the barcode which help the reader determine the direction to follow when reading the barcode.

### stopCharsBytes

A byte list representing the characters of the stop pattern of a 1D barcode.

```tsx
stopCharsBytes: number[];
```

**Remarks**

Each 1D barcode type has a unique start and stop pattern. These patterns are used to indicate the boundaries of the barcode which help the reader determine the direction to follow when reading the barcode.

### checkDigitBytes

A byte list representing the check digit of the barcode, if applicable.

```tsx
checkDigitBytes: number[];
```

**Remarks**

The check digit is a single digit that is concatenated at the end of a barcode's data in order to verify the accuracy of a scan. Different 1D barcodes have different ways to calculate the check digit.

### startPatternRange_lower

The lower bound of the start pattern range. Represents the position of the start pattern relative to the barcode location.

```tsx
startPatternRange_lower: number;
```

**Remarks**

The lower bound of this range represents the x-coordinate of the start position as a percentage.

### startPatternRange_upper

The upper bound of the start pattern range. Represents the position of the start pattern relative to the barcode location.

```tsx
startPatternRange_upper: number;
```

**Remarks**

The upper bound of this range represents the x-coordinate of the end position as a percentage.

### middlePatternRange_lower

The lower bound of the middle pattern range. Represents the position of the middle pattern relative to the barcode location.

```tsx
middlePatternRange_lower: number;
```

**Remarks**

The lower bound of this range represents the x-coordinate of the start position as a percentage.

### middlePatternRange_upper

The upper bound of the middle pattern range. Represents the position of the middle pattern relative to the barcode location.

```tsx
middlePatternRange_upper: number;
```

**Remarks**

The upper bound of this range represents the x-coordinate of the end position as a percentage.

### endPatternRange_lower

The lower bound of the end pattern range. Represents the position of the end pattern relative to the barcode location.

```tsx
endPatternRange_lower: number;
```

**Remarks**

The lower bound of this range represents the x-coordinate of the start position as a percentage.

### endPatternRange_upper

The upper bound of the end pattern range. Represents the position of the end pattern relative to the barcode location.

```tsx
endPatternRange_upper: number;
```

**Remarks**

The upper bound of this range represents the x-coordinate of the end position as a percentage.
