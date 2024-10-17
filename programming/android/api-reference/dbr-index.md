---
layout: default-layout
title: Dynamsoft Barcode Reader Android API Reference - Main Page
description: This is the main page of Dynamsoft Barcode Reader SDK API Reference for Android Language.
keywords: BarcodeReader, api reference, Android
---

# API Reference - DynamsoftBarcodeReader Library

`DynamsoftBarcodeReader` library mainly provides barcode decoding algorithms. It includes APIs for you to obtain the barcode results and configure the decoding settings.

## Namespace

### com.dynamsoft.dbr

#### APIs for General Usage

- Resulting Classes
  - Captured Result Classes
    - [BarcodeResultItem]({{ site.dbr_android_api }}barcode-result-item.html): The basic item that represents the decoding result of a single barcode.
    - [DecodedBarcodesResult]({{ site.dbr_android_api }}decoded-barcodes-result.html): All barcode decoding results that extracted from a single image.
  - Setting Configuration Classes
    - [SimplifiedBarcodeReaderSettings]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html): Configure the barcode decoding settings.
- Auxiliary Classes
  - [BarcodeReaderModule]({{ site.dbr_android_api }}barcode-reader-module.html)
- Enumerations
  - [BarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=android)
  - [DeblurMode]({{ site.dcvb_enumerations }}barcode-reader/deblur-mode.html?lang=android)
  - [ExtendedBarcodeResultType]({{ site.dcvb_enumerations }}barcode-reader/extended-barcode-result-type.html?lang=android)
  - [LocalizationMode]({{ site.dcvb_enumerations }}barcode-reader/localization-mode.html?lang=android)
  - [QRCodeErrorCorrectionLevel]({{ site.dcvb_enumerations }}barcode-reader/qr-code-error-correction-level.html?lang=android)

#### APIs for Advanced Usage

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
  - [ExtendedBarcodeResult]({{ site.dbr_android_api }}extended-barcode-result.html)
  - [LocalizedBarcodesElement]({{ site.dbr_android_api }}localized-barcode-element.html)
  - [LocalizedBarcodesUnit]({{ site.dbr_android_api }}localized-barcodes-unit.html)
  - [ScaledUpBarcodeImageUnit]({{ site.dbr_android_api }}scaled-up-barcode-image-unit.html)
