---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader Flutter Edition
description: BarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from CapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference, flutter, barcode reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a single barcode result decoded by the barcode reader. It is part of the [`DecodedBarcodesResult`](../api-reference/capture-vision-router/decoded-barcodes-result.md), which is what the library outputs at the end of the barcode recognition process.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class BarcodeResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`format`](#format) | *[EnumBarcodeFormat](./enum/barcode-format.md)* | The format of the barcode represented as [`EnumBarcodeFormat`](./enum/barcode-format.md). |
| [`formatString`](#formatstring) | *String* | The format of the barcode as a text string. |
| [`text`](#text) | *String* | The decoded text of the barcode. |
| [`bytes`](#bytes) | *Uint8List* | The raw bytes of the barcode. |
| [`location`](#location) | *Quadrilateral* | The location of the barcode in the image/frame. |
| [`confidence`](#confidence) | *int* | The confidence of the barcode result. |
| [`angle`](#angle) | *int* | The angle at which the barcode is detected if it's not aligned in the image/frame. |
| [`moduleSize`](#modulesize) | *int* | The size of the smallest module (dot or line) of the barcode. |
| [`isDPM`](#isdpm) | *bool* | Indicates whether the barcode is a Dot Peen Marking (DPM). |
| [`isMirrored`](#ismirrored) | *bool* | Indicates whether the barcode image is mirrored. |

### format

The format of the barcode represented as a [`EnumBarcodeFormat`](./enum/barcode-format.md).

```dart
EnumBarcodeFormat format;
```

### formatString

The format of the barcode as a text string instead of a `EnumBarcodeFormat`.

```dart
String formatString;
```

### text

The decoded text of the barcode.

```dart
String text;
```

### bytes

The raw bytes of the barcode.

```dart
Uint8List bytes;
```

### location

The location of the barcode in the image/frame as a `Quadrilateral`. The quadrilateral contains the four vertex points of the location, with the first vertex being the left-most vertex, then going in a clockwise direction for the remaining points.

```dart
Quadrilateral location;
```

### confidence

The confidence of the barcode result is a measure of the result's accuracy. If the confidence is lower than 30, the result will not be output by default as it is considered quite inaccurate.

```dart
int confidence;
```

### angle

The angle at which the barcode is detected if it's not aligned in the image/frame.

```dart
int angle;
```

### moduleSize

The size of the smallest module (dot or line) of the barcode.

```dart
int moduleSize;
```

### isDPM

Indicates whether the barcode is a Dot Peen Marking (DPM), which is a unique type of Datamatrix code.

```dart
bool isDPM;
```

### isMirrored

Indicates whether the barcode image is mirrored.

```dart
bool isMirrored;
```

### qrCodeDetails

Represents extended info (as [`QRCodeDetails`](qr-code-details.md)) that is specific to QR Codes, if the decoded barcode is a QR Code.

```dart
QRCodeDetails? qrCodeDetails;
```

### aztecDetails

Represents extended info (as [`AztecDetails`](aztec-details.md)) that is specific to Aztec codes, if the decoded barcode is an Aztec code.

```dart
AztecDetails? aztecDetails;
```

### dataMatrixDetails

Represents extended info (as [`DataMatrixDetails`](datamatrix-details.md)) that is specific to DataMatrix codes, if the decoded barcode is a DataMatrix code.

```dart
DataMatrixDetails? dataMatrixDetails;
```

### oneDCodeDetails

Represents extended info (as [`OneDCodeDetails`](oned-details.md)) that is specific to 1D codes, if the decoded barcode is a 1D code.

```dart
OneDCodeDetails? oneDCodeDetails;
```

### pdf417Details

Represents extended info (as [`PDF417Details`](pdf417-details.md)) that is specific to PDF417 codes, if the decoded barcode is a PDF417 code.

```dart
PDF417Details? pdf417Details;
```