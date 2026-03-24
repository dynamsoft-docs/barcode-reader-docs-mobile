---
layout: default-layout
title: Barcode Formats - Dynamsoft Barcode Reader iOS
description: Learn how barcode format configuration affects performance and correctness in Dynamsoft Barcode Reader iOS SDK.
keywords: barcode formats, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Barcode Formats

The Dynamsoft Barcode Reader SDK is designed to recognize different types of barcodes, including linear barcodes, 2-dimensional barcodes such as QR Code, PDF417, DataMatrix, MaxiCode, and Aztec Code, DataBar, GS1 Composite symbologies, Pharmacode, Patch Code, and various types of postal codes.

## How Barcode Formats Affect the Decoding Process

During decoding, the SDK attempts to match the input image against all enabled barcode formats. Each format represents a distinct decoding logic and structural rule set.

Enabling more formats means:

- More decoding branches are evaluated.
- More pattern checks are performed.
- A higher chance of cross-format interpretation in edge cases.

This makes format configuration an important factor in both performance and accuracy.

## Why Configure Barcode Formats?

1. Improve speed
   - Fewer enabled formats reduce the number of decoding attempts per frame or image.

2. Reduce misreads
   - Similar symbologies (especially among 1D formats) may produce cross-decoding results when multiple formats are enabled.

3. Align with license capabilities
   - Some licenses enable only a subset of formats.

## Supported Formats

- See an introduction to [supported barcode formats](https://www.dynamsoft.com/barcode-reader/barcode-types/){:target="_blank"}.
- View the full list in the enumeration [`EnumBarcodeFormat`]({{ site.dbr_ios_api }}enum/barcode-format.html).

## Next Step

- [How to Configure Barcode Formats]({{ site.oc }}user-guide/capabilities/barcode-formats.html)
