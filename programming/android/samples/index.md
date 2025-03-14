---
layout: default-layout
title: Demo & Samples - Dynamsoft Barcode Reader Android Edition
description: The index of Dynamsoft Barcode Reader Android demo & samples.
keywords: demo, sample, index, Android
needAutoGenerateSidebar: true
noTitleIndex: false
---

# Demo and Samples

- [Demo and Samples](#demo-and-samples)
  - [Demos](#demos)
    - [Barcode Scanner Demo](#barcode-scanner-demo)
  - [BarcodeScanner API Samples](#barcodescanner-api-samples)
    - [ScanSingleBarcode](#scansinglebarcode)
    - [ScanMultipleBarcodes](#scanmultiplebarcodes)
    - [ScenarioOrientedSamples](#scenarioorientedsamples)
  - [Foundation API Samples](#foundation-api-samples)
    - [Read Single Barcode (With CameraEnhancer)](#read-single-barcode-with-cameraenhancer)
    - [Read Single Barcode (With CameraX)](#read-single-barcode-with-camerax)
    - [Decode Barcodes from an Image](#decode-barcodes-from-an-image)
    - [Decode Multiple Barcodes from Video Stream](#decode-multiple-barcodes-from-video-stream)
    - [General Barcode Decoding Settings](#general-barcode-decoding-settings)
    - [Decode Tiny Barcodes](#decode-tiny-barcodes)
    - [Locate an Item with Barcode](#locate-an-item-with-barcode)
  - [ID Scanning Samples](#id-scanning-samples)
    - [Scan a Driver's License (via PDF417 Barcode)](#scan-a-drivers-license-via-pdf417-barcode)
  - [Other Use Case Samples](#other-use-case-samples)
    - [Scan VIN Barcode](#scan-vin-barcode)

## Demos

### Barcode Scanner Demo

- [View in Google Play Store](https://play.google.com/store/apps/details?id=com.dynamsoft.demo.dynamsoftbarcodereaderdemo&pli=1){:target="_blank"}
- [Download APK](https://download2.dynamsoft.com/dbr/android/DynamsoftBarcodeReaderDemoAndroid.apk)

## BarcodeScanner API Samples

### ScanSingleBarcode

Scan a barcode with the ready-to-use UI, `BarcodeScannerActivity`. The scanner always returns a single result. User have to select one barcode if multiple barcodes are scanned.

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/BarcodeScannerAPISamples/ScanSingleBarcode)
- [Kotlin](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/BarcodeScannerAPISamples/ScanSingleBarcodeKt)

### ScanMultipleBarcodes

Scan multiple barcodes with the ready-to-use UI, `BarcodeScannerViewController`. The scanner returns multiple results.

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/BarcodeScannerAPISamples/ScanMultipleBarcodes)

### ScenarioOrientedSamples

A collection of samples showing how to use the `BarcodeScanner` component in different scenarios including:

- High-Density QRCode
- Direct Part Marking (DPM)
- DotCode
- Aztec Code

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/BarcodeScannerAPISamples/ScenarioOrientedSamples)

## Foundation API Samples

### Read Single Barcode (With CameraEnhancer)

Decode barcodes from video streaming. It shows the simplest code to implement a video barcode scanner.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraEnhancer){:target="_blank"}

### Read Single Barcode (With CameraX)

Generally the same as `DecodeWithCameraEnhancer` but using `CameraX` library as the input.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeWithCameraX){:target="_blank"}

### Decode Barcodes from an Image

Decode barcodes from an still image. It shows how to select a image from the album and decode it.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"}

### Decode Multiple Barcodes from Video Stream

This sample shows how to efficiently decode multiple barcodes from the video stream.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/DecodeMultipleBarcodes){:target="_blank"}

### General Barcode Decoding Settings

Displays general barcode decoding settings and camera settings like barcode formats, expected barcode count and scan region settings. The default scan mode is continuous scanning.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/GeneralSettings){:target="_blank"}

### Decode Tiny Barcodes

The sample to tell you how to process the tiny barcodes including zoom and focus control.

### Locate an Item with Barcode

Input an ID with barcode text and detect it from multiple barcodes under the screen.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/FoundationalAPISamples/LocateAnItemWithBarcode){:target="_blank"}

## ID Scanning Samples

### Scan a Driver's License (via PDF417 Barcode)

Scan the PDF417 barcodes on a drivers' license and extract the drivers information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/Android/DriversLicenseScanner){:target="_blank"}

## Other Use Case Samples

### Scan VIN Barcode

Scan the vin barcode and extract the vehicle information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/Android/VINScanner){:target="_blank"}
