---
layout: default-layout
title: BarcodeResultItem Class - Dynamsoft Barcode Reader React Native Edition
description: BarcodeResultItem class represents a barcode result item decoded by barcode reader engine. It is derived from CapturedResultItem.
keywords: GetFormat, GetText, GetLocation, GetConfidence, GetModuleSize, BarcodeResultItem, api reference, flutter, barcode reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeResultItem
---

# BarcodeResultItem Class

The `BarcodeResultItem` class represents a single barcode result decoded by the barcode reader. It is part of the [`DecodedBarcodesResult`](decoded-barcodes-result.md), which is what the library outputs at the end of the barcode recognition process.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
interface BarcodeResultItem extends CapturedResultItem
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`format`](#format) | *BigInt* | The format of the barcode. |
| [`formatString`](#formatstring) | *string* | The format of the barcode as a text string. |
| [`text`](#text) | *string* | The decoded text of the barcode. |
| [`bytes`](#bytes) | *Uint8List* | The raw bytes of the barcode. |
| [`location`](#location) | *Quadrilateral* | The location of the barcode in the image/frame. |
| [`confidence`](#confidence) | *int* | The confidence of the barcode result. |
| [`angle`](#angle) | *int* | The angle at which the barcode is detected if it's not aligned in the image/frame. |
| [`moduleSize`](#modulesize) | *int* | The size of the smallest module (dot or line) of the barcode. |
| [`isDPM`](#isdpm) | *bool* | Indicates whether the barcode is a Direct Part Marking (DPM). |
| [`isMirrored`](#ismirrored) | *bool* | Indicates whether the barcode image is mirrored. |
| [`pdf417Details`](#pdf417details) | *[PDF417Details](pdf417-details.md)* | Represents extended info that is specific to PDF417 codes, if the decoded barcode is a PDF417 code. |
| [`oneDCodeDetails`](#onedcodedetails) | *[OneDCodeDetails](oned-details.md)* | Represents extended info that is specific to 1D codes, if the decoded barcode is a 1D code. |
| [`dataMatrixDetails`](#datamatrixdetails) | *[DataMatrixDetails](datamatrix-details.md)* | Represents extended info that is specific to DataMatrix codes, if the decoded barcode is a DataMatrix code. |
| [`aztecDetails`](#aztecdetails) | *[AztecDetails](aztec-details.md)* | Represents extended info that is specific to Aztec codes, if the decoded barcode is an Aztec code. |
| [`qrCodeDetails`](#qrcodedetails) | *[QRCodeDetails](qr-code-details.md)* | Represents extended info that is specific to QR Codes, if the decoded barcode is a QR Code. |

### format

The format of the barcode. One of the [`EnumBarcodeFormat`]({{ site.dcv_react_native_api }}core/enum/barcode-format.html).

```tsx
format: EnumBarcodeFormat | bigint;
```

### formatString

The format of the barcode as a text string instead of a `EnumBarcodeFormat`.

```tsx
formatString: string;
```

### text

The decoded text of the barcode.

```tsx
text: string;
```

### location

The location of the barcode in the image/frame as a [`Quadrilateral`]({{ site.dcv_react_native_api }}core/quadrilateral.html). The quadrilateral contains the four vertex points of the location, with the first vertex being the left-most vertex, then going in a clockwise direction for the remaining points.

```tsx
location: Quadrilateral;
```

### confidence

The confidence of the barcode result is a measure of the result's accuracy. If the confidence is lower than 30, the result will not be output by default as it is considered quite inaccurate.

```tsx
confidence: number;
```

### angle

The angle at which the barcode is detected if it's not aligned in the image/frame.

```tsx
angle: number;
```

### moduleSize

The size of the smallest module (dot or line) of the barcode.

```tsx
moduleSize: number;
```

### isDPM

Indicates whether the barcode is a Dot Peen Marking (DPM), which is a unique type of DataMatrix code.

```tsx
isDPM: boolean;
```

### isMirrored

Indicates whether the barcode image is mirrored.

```tsx
isMirrored: boolean;
```

### qrCodeDetails

Represents extended info (as [`QRCodeDetails`](qr-code-details.md)) that is specific to QR Codes, if the decoded barcode is a QR Code.

```tsx
qrCodeDetails?: QRCodeDetails;
```

### aztecDetails

Represents extended info (as [`AztecDetails`](aztec-details.md)) that is specific to Aztec codes, if the decoded barcode is an Aztec code.

```tsx
aztecDetails?: AztecDetails;
```

### dataMatrixDetails

Represents extended info (as [`DataMatrixDetails`](datamatrix-details.md)) that is specific to DataMatrix codes, if the decoded barcode is a DataMatrix code.

```tsx
dataMatrixDetails?: DataMatrixDetails;
```

### oneDCodeDetails

Represents extended info (as [`OneDCodeDetails`](oned-details.md)) that is specific to 1D codes, if the decoded barcode is a 1D code.

```tsx
oneDCodeDetails?: OneDCodeDetails;
```

### pdf417Details

Represents extended info (as [`PDF417Details`](pdf417-details.md)) that is specific to PDF417 codes, if the decoded barcode is a PDF417 code.

```tsx
pdf417Details?: PDF417Details;
```