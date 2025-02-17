---
layout: default-layout
title: Demo & Samples - Dynamsoft Barcode Reader iOS Edition
description: The index of Dynamsoft Barcode Reader iOS demo & samples.
keywords: demo, sample, index, iOS
needAutoGenerateSidebar: true
noTitleIndex: false
---

# Demo and Samples

- [Demo and Samples](#demo-and-samples)
	- [Demos](#demos)
	- [BarcodeScanner API Samples](#barcodescanner-api-samples)
		- [ScanSingleBarcode](#scansinglebarcode)
	- [Foundational API Samples](#foundational-api-samples)
		- [Read Single Barcode (With CameraEnhancer)](#read-single-barcode-with-cameraenhancer)
		- [Read Single Barcode (With AVCaptureSession)](#read-single-barcode-with-avcapturesession)
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

- Barcode Scanner Demo
  - [View in App Store](https://apps.apple.com/us/app/dynamsoft-barcode-scanner-demo/id1120581630){:target="_blank"}

## BarcodeScanner API Samples

### ScanSingleBarcode

Scan a barcode with the ready-to-use UI, `BarcodeScannerViewController`. The scanner always returns a single result. User have to select one barcode if multiple barcodes are scanned.

Check code on GitHub

- [Swift](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanSingleBarcode)
- [Objective-C](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/BarcodeScannerAPISamples/ScanSingleBarcodeObjc)

## Foundational API Samples

### Read Single Barcode (With CameraEnhancer)

Decode barcodes from video streaming. It shows the simplest code to implement a video barcode scanner.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithCameraEnhancer){:target="_blank"}

### Read Single Barcode (With AVCaptureSession)

Generally the same as `DecodeWithCameraEnhancer` but using `AVCaptureSession` library as the input.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithAVCaptureSession){:target="_blank"}

### Decode Barcodes from an Image

Decode barcodes from an still image. It shows how to select a image from the album and decode it.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeFromAnImage){:target="_blank"}

### Decode Multiple Barcodes from Video Stream

This sample shows how to efficiently decode multiple barcodes from the video stream.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeMultipleBarcodes){:target="_blank"}

### General Barcode Decoding Settings

Displays general barcode decoding settings and camera settings like barcode formats, expected barcode count and scan region settings. The default scan mode is continuous scanning.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/GeneralSettings){:target="_blank"}

### Decode Tiny Barcodes

The sample to tell you how to process the tiny barcodes. Including zoom and focus control.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/TinyBarcodeDecoding){:target="_blank"}

### Locate an Item with Barcode

Input an ID with barcode text and detect it from multiple barcodes under the screen.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/LocateAnItemWithBarcode){:target="_blank"}

## ID Scanning Samples

### Scan a Driver's License (via PDF417 Barcode)

Scan the PDF417 barcodes on a drivers' license and extract the drivers information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DriversLicenseScanner){:target="_blank"}

## Other Use Case Samples

### Scan VIN Barcode

Scan the vin barcode and extract the vehicle information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/VINScanner){:target="_blank"}
