---
layout: default-layout
title: Demo & Samples - Dynamsoft Barcode Reader Android Edition
description: The index of Dynamsoft Barcode Reader Android demo & samples.
keywords: demo, sample, index, Android
needAutoGenerateSidebar: true
noTitleIndex: false
---

# Android Barcode Scanner Demo & Samples

- [Android Barcode Scanner Demo \& Samples](#android-barcode-scanner-demo--samples)
  - [Demos](#demos)
    - [Android Barcode Scanner Demo](#android-barcode-scanner-demo)
  - [Android BarcodeScanner Samples](#android-barcodescanner-samples)
    - [ScanSingleBarcode](#scansinglebarcode)
    - [ScanMultipleBarcodes](#scanmultiplebarcodes)
    - [ScenarioOrientedSamples](#scenarioorientedsamples)
  - [Android Foundational API Samples](#android-foundational-api-samples)
    - [Read Single Barcode (With CameraEnhancer)](#read-single-barcode-with-cameraenhancer)
    - [Read Single Barcode (With CameraX)](#read-single-barcode-with-camerax)
    - [Decode Barcodes from an Image](#decode-barcodes-from-an-image)
    - [General Barcode Decoding Settings](#general-barcode-decoding-settings)
    - [Decode Tiny Barcodes](#decode-tiny-barcodes)
    - [Locate an Item with Barcode](#locate-an-item-with-barcode)
  - [Android ID Scanning Samples](#android-id-scanning-samples)
    - [Scan a Driver's License (via PDF417 Barcode)](#scan-a-drivers-license-via-pdf417-barcode)
  - [Other Use Case Samples for Android Platform](#other-use-case-samples-for-android-platform)
    - [Scan VIN Barcode](#scan-vin-barcode)

## Demos

### Android Barcode Scanner Demo

- [View in Google Play Store](https://play.google.com/store/apps/details?id=com.dynamsoft.demo.dynamsoftbarcodereaderdemo&pli=1){:target="_blank"}
- [Download APK](https://download2.dynamsoft.com/dbr/android/DynamsoftBarcodeReaderDemoAndroid.apk)

## Android BarcodeScanner Samples

The `BarcodeScanner` Android examples show you how to develop and customize your scanner app with the Ready-to-Use component, `BarcodeScanner`, of Dynamsoft Barcode Reader.

### ScanSingleBarcode

Scan a barcode with the ready-to-use UI, `BarcodeScannerActivity`. The scanner always returns a single result. User have to select one barcode if multiple barcodes are scanned.

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/BarcodeScannerAPISamples/ScanSingleBarcode)
- [Kotlin](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/BarcodeScannerAPISamples/ScanSingleBarcodeKt)

### ScanMultipleBarcodes

Scan multiple barcodes with the ready-to-use UI, `BarcodeScannerViewController`. The scanner returns multiple results.

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/BarcodeScannerAPISamples/ScanMultipleBarcodes)

### ScenarioOrientedSamples

A collection of samples showing how to use the `BarcodeScanner` component in different scenarios including:

- High-Density QRCode
- Direct Part Marking (DPM)
- DotCode
- Aztec Code

Check code on GitHub

- [Java](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/BarcodeScannerAPISamples/ScenarioOrientedSamples)

## Android Foundational API Samples

The foundational API examples show you how to use the foundational APIs of Dynamsoft Barcoder Reader to develop a full customizable iOS barcode scanner.

### Read Single Barcode (With CameraEnhancer)

Decode barcodes from video streaming. It shows the simplest code to implement a video barcode scanner.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/FoundationalAPISamples/DecodeWithCameraEnhancer){:target="_blank"}

### Read Single Barcode (With CameraX)

Generally the same as `DecodeWithCameraEnhancer` but using `CameraX` library as the input.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/FoundationalAPISamples/DecodeWithCameraX){:target="_blank"}

### Decode Barcodes from an Image

Decode barcodes from an still image. It shows how to select a image from the album and decode it.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"}

### General Barcode Decoding Settings

Displays general barcode decoding settings and camera settings like barcode formats, expected barcode count and scan region settings. The default scan mode is continuous scanning.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/FoundationalAPISamples/GeneralSettings){:target="_blank"}

### Decode Tiny Barcodes

The sample to tell you how to process the tiny barcodes including zoom and focus control.

### Locate an Item with Barcode

Input an ID with barcode text and detect it from multiple barcodes under the screen.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.3000/android/FoundationalAPISamples/LocateAnItemWithBarcode){:target="_blank"}

## Android ID Scanning Samples

### Scan a Driver's License (via PDF417 Barcode)

Scan the PDF417 barcodes on a drivers' license and extract the drivers information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/dcv_v2.6.1003/Android/DriversLicenseScanner){:target="_blank"}

## Other Use Case Samples for Android Platform

### Scan VIN Barcode

Scan the vin barcode and extract the vehicle information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/Android/VINScanner){:target="_blank"}
