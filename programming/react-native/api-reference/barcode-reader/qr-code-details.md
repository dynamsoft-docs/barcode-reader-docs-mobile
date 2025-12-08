---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Capture Vision React Native
description: QRCodeDetails class of DCV React Native represents the extended info of a QR Code.
keywords: qr code, details, result, barcode, extended
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# QRCodeDetails

The `QRCodeDetails` class encapsulates all of the extended details of a QR Code that is not available in the regular barcode result, if the barcode is a QR Code. 

> [!TIP]
> If you would like to learn more about the QR Code format, please refer to this [page](https://www.dynamsoft.com/barcode-reader/barcode-types/qr-code/).

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
interface QRCodeDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`rows`](#rows) | *number* | Represents the number of rows that make up the QR Code. |
| [`columns`](#columns) | *number* | Represents the number of columns that make up the QR Code. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *EnumQRCodeErrorCorrectionLevel* | Represents the error correction level of the QR Code as a [`EnumQRCodeErrorCorrectionLevel`](enum/qr-code-correction.md). |
| [`version`](#version) | *number* | Represents the version of the QR Code. |
| [`model`](#model) | *number* | Represents the number of models of the QR Code. |
| [`mode`](#mode) | *number* | Identifies the first data encoding mode of the QR Code. |
| [`page`](#page) | *number* | Identifies the position of the particular symbol (as in this specific QR Code) in the Structured Append format of the overall QR Code. |
| [`totalPage`](#totalpage) | *number* | The total number of symbols to be concatenated into the Structured Append format of the QR Code. |
| [`parityData`](#paritydata) | *number* | The Parity Data of the QR Code. |
| [`dataMaskPattern`](#datamaskpattern) | *number* | Represents the data mask pattern reference for the QR Code symbols. |
| [`codewords`](#codewords) | *number[]* | The codewords of the QR Code. |

### rows

Represents the number of rows that make up the QR Code. 

```tsx
rows: number;
```

### columns

Represents the number of columns that make up the QR Code.

```tsx
columns: number;
```

### errorCorrectionLevel

Represents the error correction level of the QR Code as a [`EnumQRCodeErrorCorrectionLevel`](enum/qr-code-correction.md).

```tsx
errorCorrectionLevel: number;
```

**Remarks**

There are four levels of error correction that determine how much damage a QR Code can sustain and still be readable. The error correction level is determined when the QR Code is generated, and then later gets encoded into the final QR code image.

### version

Represents the version of the QR Code. 

```tsx
version: number;
```

### model

Represents the number of models of the QR Code.

```tsx
model: number;
```

### mode

Identifies the first data encoding mode of the QR Code.

```tsx
mode: number;
```

### page

Identifies the position of the particular symbol (as in this specific QR Code) in the Structured Append format of the overall QR Code.

```tsx
page: number;
```

**Remarks**

Structured Append is a QR Code feature that is used to split a (typically) large message across several QR Codes. This comes in handy for data that would typically be too large to fit into a single QR Code. In these cases, each QR Code contains extra metadata indicating its position in the sequence as well as the total number of codes in the sequence.

### totalPage

Identifies the total number of symbols to be concatenated in the Structured Append format of the QR Code.

```tsx
totalPage: number;
```

**Remarks**

Structured Append is a QR Code feature that is used to split a (typically) large message across several QR Codes. This comes in handy for data that would typically be too large to fit into a single QR Code. In these cases, each QR Code contains extra metadata indicating its position in the sequence as well as the total number of codes in the sequence.

### parityData

Identifies the unique parity identifier of the QR Code in the Structured Append format. The parity identifier allows the library to confirm that the QR Codes of the Structured Append format belong to the same group.

```tsx
parityData: number;
```

**Remarks**

Structured Append is a QR Code feature that is used to split a (typically) large message across several QR Codes. This comes in handy for data that would typically be too large to fit into a single QR Code. The Parity Data shall be an 8-bit byte following the Symbol Sequence indicator. The parity data is a value obtained by XORing  the ASCII/JIS values of all the original input data byte by byte before division into symbol blocks.

### dataMaskPattern

Represents the data mask pattern reference for the QR Code symbols.

```tsx
dataMaskPattern: number;
```

**Remarks**

A data mask pattern prevents large blocks of black or white modules that could confuse a scanner. There are eight mask patterns, with each having its own unique formula to determine whether to invert the colour of each module. The process of choosing one of the eight mask patterns is determined by the generator, assessing which pattern will lead to the lowest penalty score. This score is calculated based on a variety of factors that are defined in the QR Code specification.

### codewords

Represents the fundamental data units (or codewords) that are used to store the encoded data of a QR Code as well as the error correction info.

```tsx
codewords: number[];
```

**Remarks**

Typically in a QR Code, there are data codewords and error correction codewords. Data codewords contain the actual info encoded onto the QR Code, while the error correction codewords are extra codewords that contain unnecessary or superfluous data. These error correction codewords help the reader identify the QR Code even if it's damaged or distorted in some way. 


