---
layout: default-layout
title: OneDCodeDetails Class - Dynamsoft Barcode Reader MAUI Edition
description: The OneDCodeDetails class of Dynamsoft Barcode Reader MAUI edition represents a barcode in OneD format.
keywords: OneDCodeDetails, api reference, start char bytes, stop char bytes, pattern range, check digit
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: OneDCodeDetails
---

# OneDCodeDetails

`OneDCodeDetails` represents detailed information specific to a 1D (one dimensional) barcode.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class OneDCodeDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`StartCharsBytes`](#startcharsbytes) | *byte[]?* | The start characters of the 1D barcode in a byte array. |
| [`StopCharsBytes`](#stopcharsbytes) | *byte[]?* | The stop characters of the 1D barcode in a byte array. |
| [`CheckDigitBytes`](#checkdigitbytes) | *byte[]?* | The check digit characters of the 1D barcode in a byte array. |
| [`StartPatternRange`](#startpatternrange) | *ValueTuple<float, float>* | The position range of the start pattern relative to the barcode's location. |
| [`MiddlePatternRange`](#middlepatternrange) | *ValueTuple<float, float>* | The position range of the middle pattern relative to the barcode's location. |
| [`EndPatternRange`](#endpatternrange) | *ValueTuple<float, float>* | The position of the end pattern relative to the barcode location. |

### StartCharsBytes

The start characters of the 1D barcode in a byte array. Start characters are often used to identify the beginning of the barcode.

```csharp
byte[]? StartCharsBytes { get; }
```

### StopCharsBytes

The stop characters of the 1D barcode in a byte array. Stop characters are often used to identify the end of the barcode.

```csharp
byte[]? StopCharsBytes { get; }
```

### CheckDigitBytes

The check digit characters of the 1D barcode in a byte array. Check digits are used for error detection and correction in some 1D barcodes.

```csharp
byte[]? CheckDigitBytes { get; }
```

### StartPatternRange

The position range of the start pattern relative to the barcode's location.

```csharp
(float Start, float End) StartPatternRange { get; }
```

### MiddlePatternRange

The position range of the middle pattern relative to the barcode's location.


```csharp
(float Start, float End) MiddlePatternRange { get; }
```

### EndPatternRange

The position range of the end pattern relative to the barcode's location.

```csharp
(float Start, float End) EndPatternRange { get; }
```
