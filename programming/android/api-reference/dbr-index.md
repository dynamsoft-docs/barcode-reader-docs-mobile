---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Android Language.
keywords: BarcodeReader, api reference, Android
---

# API Reference - DynamsoftBarcodeReader Library

`DynamsoftBarcodeReader` library mainly provides barcode decoding algorithms. It includes APIs for you to obtain the barcode results and configure the decoding settings.

- Settings
  - [SimplifiedBarcodeReaderSettings]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html): Configure the barcode decoding settings.
- Resulting Classes
  - Basic Barcode Results
    - [DecodedBarcodesResult]({{ site.dbr_android_api }}decoded-barcodes-result.html): All barcode decoding results that extracted from a single image.
    - [BarcodeResultItem]({{ site.dbr_android_api }}barcode-result-item.html): The basic item that represents the decoding result of a single barcode.
  - Barcode Details
    - [AztecDetails]({{ site.dbr_android_api }}auxiliary-AztecDetails.html)
    - [BarcodeDetails]({{ site.dbr_android_api }}barcode-details.html)
    - [DataMatrixDetails]({{ site.dbr_android_api }}auxiliary-DatamatrixDetails.html)
    - [OneDCodeDetails]({{ site.dbr_android_api }}auxiliary-OneDCodeDetails.html)
    - [PDF417Details]({{ site.dbr_android_api }}auxiliary-PDF417Details.html)
    - [QRCodeDetails]({{ site.dbr_android_api }}auxiliary-QRCodeDetails.html)
  - Intermediate Result Classes
    - [CandidateBarcodeZonesUnit]({{ site.dbr_android_api }}candidate-barcode-zones-unit.html)
    - [CandidateBarcodeZone]({{ site.dbr_android_api }}candidate-barcode-zone.html)
    - [ComplementedBarcodeImageUnit]({{ site.dbr_android_api }}complemented-barcode-image-unit.html)
    - [DecodedBarcodeElement]({{ site.dbr_android_api }}decoded-barcode-element.html)
    - [DecodedBarcodesUnit]({{ site.dbr_android_api }}decoded-barcodes-unit.html)
    - [DeformationResistedBarcodeImageUnit]({{ site.dbr_android_api }}deformation-resisted-barcode-image-unit.html)
    - [DeformationResistedBarcode]({{ site.dbr_android_api }}deformation-resisted-barcode.html)
    - [ECISegment]({{ site.dbr_android_api }}eci-segment.html)
    - [ExtendedBarcodeResult]({{ site.dbr_android_api }}auxiliary-ExtendedResult.html)
    - [LocalizedBarcodesElement]({{ site.dbr_android_api }}localized-barcode-element.html)
    - [LocalizedBarcodesUnit]({{ site.dbr_android_api }}localized-barcodes-unit.html)
    - [ScaledUpBarcodeImageUnit]({{ site.dbr_android_api }}scaled-up-barcode-image-unit.html)
- Auxiliary Classes
  - [BarcodeReaderModule]({{ site.dbr_android_api }}barcode-reader-module.html)
- Enumerations
  - [BarcodeFormat]({{ site.dbr_android_api }}enum/barcode-format.html)
  - [DeblurMode]({{ site.dbr_android_api }}enum/deblur-mode.html)
  - [ExtendedBarcodeResultType]({{ site.dbr_android_api }}enum/extended-barcode-result-type.html)
  - [LocalizationMode]({{ site.dbr_android_api }}enum/localization-mode.html)
  - [QRCodeErrorCorrectionLevel]({{ site.dbr_android_api }}enum/qr-code-error-correction-level.html)
