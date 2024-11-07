---
layout: default-layout
title: Demo & Samples - Dynamsoft Barcode Reader iOS Edition
description: The index of Dynamsoft Barcode Reader iOS demo & samples.
keywords: demo, sample, index, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Demo & Samples

- [Demo & Samples](#demo--samples)
  - [Demos](#demos)
  - [Barcode Decoding Samples](#barcode-decoding-samples)
    - [Read Single Barcode (With CameraEnhancer)](#read-single-barcode-with-cameraenhancer)
    - [Read Single Barcode (With AVCaptureSession)](#read-single-barcode-with-avcapturesession)
    - [Decode Barcodes from an Image](#decode-barcodes-from-an-image)
    - [Decode Multiple Barcodes from Video Stream](#decode-multiple-barcodes-from-video-stream)
    - [General Barcode Decoding Settings](#general-barcode-decoding-settings)
    - [Barcode Decoding Performance Settings](#barcode-decoding-performance-settings)
    - [Decode Tiny Barcodes](#decode-tiny-barcodes)
    - [Locate an Item with Barcode](#locate-an-item-with-barcode)
  - [ID Scanning Samples](#id-scanning-samples)
    - [Scan a Driver's License (via PDF417 Barcode)](#scan-a-drivers-license-via-pdf417-barcode)
  - [Other Use Case Samples](#other-use-case-samples)
    - [Scan VIN Barcode](#scan-vin-barcode)

## Demos

- Barcode Scanner Demo
  - [View in Apple Store](https://apps.apple.com/us/app/dynamsoft-barcode-scanner-demo/id1120581630){:target="_blank"}

<!-- - MRZ Scanner Demo
  - [View in Apple Store](https://apps.apple.com/us/app/dynamsoft-mrz-scanner-demo/id1120581630){:target="_blank"} -->

## Barcode Decoding Samples

### Read Single Barcode (With CameraEnhancer)

Decode barcodes from video streaming. It shows the simplest code to implement a video barcode scanner.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/HelloWorld/DecodeWithCameraEnhancer){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/5d6adaed-976f-40aa-9f58-19980f801ba7">
</video>

### Read Single Barcode (With AVCaptureSession)

Generally the same as `DecodeWithCameraEnhancer` but using `AVCaptureSession` library as the input.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/HelloWorld/DecodeWithAVCaptureSession){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/5d6adaed-976f-40aa-9f58-19980f801ba7">
</video>

### Decode Barcodes from an Image

Decode barcodes from an still image. It shows how to select a image from the album and decode it.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/HelloWorld/DecodeFromAnImage){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/9f13ada8-b253-43a0-8121-60bbebed4696">
</video>

### Decode Multiple Barcodes from Video Stream

This sample shows how to efficiently decode multiple barcodes from the video stream.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/DecodeMultipleBarcodes){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/63a10ebf-34a1-438f-9673-9fbf8c408dd1">
</video>

### General Barcode Decoding Settings

Displays general barcode decoding settings and camera settings like barcode formats, expected barcode count and scan region settings. The default scan mode is continuous scanning.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/GeneralSettings){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/8e97909e-2a67-406d-bbd1-41a8e5810210">
</video>

### Barcode Decoding Performance Settings

Parameter configuration guide on improving the speed, read-rate and accuracy of barcode reading. The sample includes the code of image decoding from the album.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/PerformanceSettings){:target="_blank"}

<!-- <video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/108aa022-15b6-4e27-8c47-fbe8f89b0356">
</video> -->

### Decode Tiny Barcodes

The sample to tell you how to process the tiny barcodes. Including zoom and focus control.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/UseCase/TinyBarcodeDecoding){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/f6881a36-3858-49d0-9458-5b732c96273d">
</video>

### Locate an Item with Barcode

Input an ID with barcode text and detect it from multiple barcodes under the screen.

[Check code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/UseCase/LocateAnItemWithBarcode){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/9101cd5a-fc67-4650-aaef-1e5270a29a25">
</video>

## ID Scanning Samples

### Scan a Driver's License (via PDF417 Barcode)

Scan the PDF417 barcodes on a drivers' license and extract the drivers information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/DriversLicenseScanner){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/338a0bcc-afa0-4afd-8372-14373a112d36">
</video>

## Other Use Case Samples

### Scan VIN Barcode

Scan the vin barcode and extract the vehicle information.

[Check code on GitHub](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/ios/VINScanner){:target="_blank"}

<video controls width="250" autoplay="false">
    <source src="https://github.com/user-attachments/assets/5d3200a0-1c9f-4428-a58b-f9d7a5a28693">
</video>
