---
layout: default-layout
title: Demo & Samples - Dynamsoft Barcode Reader iOS Edition
description: The index of Dynamsoft Barcode Reader iOS demo & samples.
keywords: demo, sample, index, iOS
needAutoGenerateSidebar: true
noTitleIndex: false
---

# iOS Barcode Scanner Demo & Samples

- [iOS Barcode Scanner Demo \& Samples](#ios-barcode-scanner-demo--samples)
	- [iOS Barcode Scanner Demos](#ios-barcode-scanner-demos)
	- [iOS BarcodeScanner API Samples](#ios-barcodescanner-api-samples)
		- [ScanSingleBarcode](#scansinglebarcode)
		- [ScanMultipleBarcodes](#scanmultiplebarcodes)
		- [ScenarioOrientedSamples](#scenarioorientedsamples)
	- [iOS Foundational API Samples](#ios-foundational-api-samples)
		- [Read Single Barcode (With CameraEnhancer)](#read-single-barcode-with-cameraenhancer)
		- [Read Single Barcode (With AVCaptureSession)](#read-single-barcode-with-avcapturesession)
		- [Decode Barcodes from an Image](#decode-barcodes-from-an-image)
		- [General Barcode Decoding Settings](#general-barcode-decoding-settings)
		- [Decode Tiny Barcodes](#decode-tiny-barcodes)
		- [Locate an Item with Barcode](#locate-an-item-with-barcode)
	- [iOS ID Scanning Samples](#ios-id-scanning-samples)
		- [Scan a Driver's License (via PDF417 Barcode)](#scan-a-drivers-license-via-pdf417-barcode)
	- [Other Use Case Samples for iOS Platform](#other-use-case-samples-for-ios-platform)
		- [Scan VIN Barcode](#scan-vin-barcode)

## iOS Barcode Scanner Demos

- Barcode Scanner Demo
  - [View in App Store](https://apps.apple.com/us/app/dynamsoft-barcode-scanner-demo/id1120581630){:target="_blank"}

## iOS BarcodeScanner API Samples

The `BarcodeScanner` iOS examples show you how to develop and customize your scanner app with the Ready-to-Use component, `BarcodeScanner`, of Dynamsoft Barcode Reader.

### ScanSingleBarcode

Scan a barcode with the ready-to-use UI, `BarcodeScannerViewController`. The scanner always returns a single result. User have to select one barcode if multiple barcodes are scanned.

Check code on GitHub

- [Swift](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanSingleBarcode)
- [Objective-C](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanSingleBarcodeObjc)

### ScanMultipleBarcodes

Scan multiple barcodes with the ready-to-use UI, `BarcodeScannerViewController`. The scanner returns multiple results.

Check code on GitHub

- [Swift](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanMultipleBarcodes)

### ScenarioOrientedSamples

A collection of samples showing how to use the `BarcodeScanner` component in different scenarios including:

- High-Density QRCode
- Direct Part Marking (DPM)
- DotCode
- Aztec Code

Check code on GitHub

- [Swift](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScenarioOrientedSamples)

## iOS Foundational API Samples

The foundational API examples show you how to use the foundational APIs of Dynamsoft Barcoder Reader to develop a full customizable iOS barcode scanner.

### Read Single Barcode (With CameraEnhancer)

Decode barcodes from video streaming. It shows the simplest code to implement a video barcode scanner.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithCameraEnhancer){:target="_blank"}

### Read Single Barcode (With AVCaptureSession)

Generally the same as `DecodeWithCameraEnhancer` but using `AVCaptureSession` library as the input.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithAVCaptureSession){:target="_blank"}

### Decode Barcodes from an Image

Decode barcodes from an still image. It shows how to select a image from the album and decode it.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"}

### General Barcode Decoding Settings

Displays general barcode decoding settings and camera settings like barcode formats, expected barcode count and scan region settings. The default scan mode is continuous scanning.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/GeneralSettings){:target="_blank"}

### Decode Tiny Barcodes

The sample to tell you how to process the tiny barcodes. Including zoom and focus control.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/TinyBarcodeDecoding){:target="_blank"}

### Locate an Item with Barcode

Input an ID with barcode text and detect it from multiple barcodes under the screen.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/LocateAnItemWithBarcode){:target="_blank"}

## iOS ID Scanning Samples

### Scan a Driver's License (via PDF417 Barcode)

Scan the PDF417 barcodes on a drivers' license and extract the drivers information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/dcv_v2.6.1003/ios/DriversLicenseScanner){:target="_blank"}

## Other Use Case Samples for iOS Platform

### Scan VIN Barcode

Scan the vin barcode and extract the vehicle information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/VINScanner){:target="_blank"}
