---
layout: default-layout
title: PDF417Details Class - Dynamsoft Capture Vision React Native
description: PDF417Details class of DCV React Native represents the extended info of a PDF417 Code.
keywords: PDF417 code, details, result, barcode, extended
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# PDF417Details

The `PDF417Details` class encapsulates all of the extended details of a PDF417 Code that is not available in the regular barcode result, if the barcode is a PDF417 Code.

> [!TIP]
> If you would like to learn more about the PDF417 format, please refer to this [page](https://www.dynamsoft.com/barcode-reader/barcode-types/pdf417/).

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface PDF417Details
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`rows`](#rows) | *number* | Represents the number of rows that make up the PDF417 Code. |
| [`columns`](#columns) | *number* | Represents the number of columns that make up the PDF417 Code. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *EnumQRCodeErrorCorrectionLevel* | Specifies the error correction level of the PDF417 Code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *boolean* | Indicates whether the PDF417 code has the left row indicator or not. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *boolean* | Indicates whether the PDF417 code has the right row indicator or not. |
| [`codewords`](#codewords) | *number* | The code words of the PDF417 Code. |

### rows

Represents the number of rows that make up the PDF417 Code. 

```js
rows: number;
```

### columns

Represents the number of columns that make up the PDF417 Code.

```js
columns: number;
```

### errorCorrectionLevel

Specifies the error correction level of the PDF417 Code.

```js
errorCorrectionLevel: EnumQRCodeErrorCorrectionLevel;
```

**Remarks**

There are eight levels for error correction when it comes to PDF417 codes, with each level indicating the readability of the PDF417 code even though it has been damaged or distorted. If you would like to learn more about the error correction levels and the differences between them, please refer to this [PDF417 info page](https://www.dynamsoft.com/barcode-reader/barcode-types/pdf417/).

### hasLeftRowIndicator

Indicates whether the PDF417 code has the left row indicator or not. 

```js
hasLeftRowIndicator: boolean;
```

**Remarks**

The left and right indicators do not contain any text data, but rather contains more of the metadata of the PDF417 code, like the number of rows, the error correction level, and more.

### hasRightRowIndicator

Indicates whether the PDF417 code has the right row indicator or not. 

```js
hasRightRowIndicator: boolean;
```

**Remarks**

The left and right indicators do not contain any text data, but rather contains more of the metadata of the PDF417 code, like the number of rows, the error correction level, and more.

### codewords

Represents the codewords of the PDF417 code.

```js
codewords: number[];
```

**Remarks**

The data codewords section is where numbers, letters, or other symbols are decoded in a cluster pattern of bars and spaces, each separated by a solid white column. There can be as few as one or as many as 30 data codeword clusters. The size of the PDF417 barcode depends on how much data is encoded.
