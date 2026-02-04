---
layout: default-layout
title: Understand Barcode Results - Dynamsoft Barcode Reader for Android
description: Understand the structure of the barcode decoding results of Dynamsoft Barcode Reader Android.
keywords: understand results, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Understand Barcode Results

- `Barcodes`
    - `BarcodeResultItem`
- `ResultStatus`
- `ErrorCode`
- `ErrorString`

- `BarcodeResultItem`
  - Format
  - FormatString
  - Text
  - byte[] Bytes
  - Quadrilateral Location
    - Point[] Points
  - int Confidence
  - int Angle
  - int ModuleSize
  - BarcodeDetails Details
    - AztecDetails
    - QRCodeDetails
    - OneDCodeDetails
    - DataMatrixDetails
    - PDF417Details
  - boolean isDPM
  - boolean isMirrored
  - ECISegment[] ECISegments
    - eciValue
    - charsetEncoding
    - startIndex
    - length