---
layout: default-layout
title: Dynamsoft Barcode Reader iOS API Reference - DynamsoftBarcodeReader
description: This is the DynamsoftBarcodeReader library reference page of Dynamsoft Barcode Reader SDK API Reference for iOS.
keywords: BarcodeReader, api reference, iOS
---

# API Reference - DynamsoftBarcodeReader Library

`DynamsoftBarcodeReader` library mainly provides barcode decoding algorithms. It includes APIs for you to obtain the barcode results and configure the decoding settings.

- Settings
  - [DSSimplifiedBarcodeReaderSettings]({{ site.dbr_ios_api }}simplified-barcode-reader-settings.html): Configure the barcode decoding settings.
- Resulting Classes
  - Basic Barcode Results
    - [DSDecodedBarcodesResult]({{ site.dbr_ios_api }}decoded-barcodes-result.html): All barcode decoding results that extracted from a single image.
    - [DSBarcodeResultItem]({{ site.dbr_ios_api }}barcode-result-item.html): The basic item that represents the decoding result of a single barcode.
  - Barcode Details
    - [DSAztecDetails]({{ site.dbr_ios_api }}auxiliary-iAztecDetails.html)
    - [DSBarcodeDetails]({{ site.dbr_ios_api }}barcode-details.html)
    - [DSDataMatrixDetails]({{ site.dbr_ios_api }}auxiliary-iDatamatrixDetails.html)
    - [DSOneDCodeDetails]({{ site.dbr_ios_api }}auxiliary-iOneDCodeDetails.html)
    - [DSPDF417Details]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html)
    - [DSQRCodeDetails]({{ site.dbr_ios_api }}auxiliary-iQRCodeDetails.html)
  - Intermediate Result Classes
    - [DSCandidateBarcodeZonesUnit]({{ site.dbr_ios_api }}candidate-barcode-zones-unit.html)
    - [DSCandidateBarcodeZone]({{ site.dbr_ios_api }}candidate-barcode-zone.html)
    - [DSComplementedBarcodeImageUnit]({{ site.dbr_ios_api }}complemented-barcode-image-unit.html)
    - [DSDecodedBarcodeElement]({{ site.dbr_ios_api }}decoded-barcode-element.html)
    - [DSDecodedBarcodesUnit]({{ site.dbr_ios_api }}decoded-barcodes-unit.html)
    - [DSDeformationResistedBarcodeImageUnit]({{ site.dbr_ios_api }}deformation-resisted-barcode-image-unit.html)
    - [DSDeformationResistedBarcode]({{ site.dbr_ios_api }}deformation-resisted-barcode.html)
    - [DSECISegment]({{ site.dbr_ios_api }}eci-segment.html)
    - [DSExtendedBarcodeResult]({{ site.dbr_ios_api }}auxiliary-iExtendedResult.html)
    - [DSLocalizedBarcodesElement]({{ site.dbr_ios_api }}localized-barcode-element.html)
    - [DSLocalizedBarcodesUnit]({{ site.dbr_ios_api }}localized-barcodes-unit.html)
    - [DSScaledUpBarcodeImageUnit]({{ site.dbr_ios_api }}scaled-up-barcode-image-unit.html)
- Auxiliary Classes
  - [DSBarcodeReaderModule]({{ site.dbr_ios_api }}barcode-reader-module.html)
- Enumerations
  - [DSBarcodeFormat]({{ site.dbr_ios_api }}enum/barcode-format.html)
  - [DSDeblurMode]({{ site.dbr_ios_api }}enum/deblur-mode.html)
  - [DSExtendedBarcodeResultType]({{ site.dbr_ios_api }}enum/extended-barcode-result-type.html)
  - [DSLocalizationMode]({{ site.dbr_ios_api }}enum/localization-mode.html)
  - [DSQRCodeErrorCorrectionLevel]({{ site.dbr_ios_api }}enum/qr-code-error-correction-level.html)
