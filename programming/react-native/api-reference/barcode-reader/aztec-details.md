---
layout: default-layout
title: AztecDetails Class - Dynamsoft Capture Vision React Native
description: AztecDetails class of DCV React Native represents the extended info of a QR Code.
keywords: aztec code, details, result, barcode, extended
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# AztecDetails

The `AztecDetails` class encapsulates all of the extended details of an Aztec Code that is not available in the regular barcode result, if the barcode is an Aztec Code. 

> [!TIP]
> If you would like to learn more about the Aztec format, please refer to this [page](https://www.dynamsoft.com/barcode-reader/barcode-types/aztec-code/).

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface AztecDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`rows`](#rows) | *number* | Represents the number of rows that make up the Aztec Code. |
| [`columns`](#columns) | *number* | Represents the number of columns that make up the Aztec Code. |
| [`layerNumber`](#layernumber) | *number* | Represents the layer number of an Aztec code.|

### rows

Represents the number of rows that make up the Aztec Code. 

```js
rows: number;
```

### columns

Represents the number of columns that make up the Aztec Code.

```js
columns: number;
```

### layerNumber

Represents the layer number of an Aztec code. A negative number (-1, -2, -3, -4) specifies a compact Aztec code, while a positive number (1, 2,...32) specifies a normal (full-range) Aztec code.

```js
layerNumber: number;
```

**Remarks**

When it comes to Aztec codes, there are two main sizes that the Barcode Reader library supports. The first is the compact Aztec code, which has 1 to 4 layers, and it is used for smaller pieces of data or messages. The second is a full-range Aztec code, which has 1 to 32 layers, and it is used for larger pieces of data or messages.

