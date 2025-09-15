---
layout: default-layout
title: The index of Xamarin API Reference
description: This page is the index of Xamarin API reference
keywords: API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: API Index
---

# Xamarin API Reference

## namespace DCVXamarin

### Primary Classess/Interfaces

| Classes | Description |
| ------- | ----------- |
| [`IDCVBarcodeReader`](barcode-reader.md) | The interface that contains barcode decoding related APIs. |
| [`IDCVCameraEnhancer`](camera-enhancer.md) | The interface that contains camera control and camera enhancements related APIs. |
| [`CameraView`](camera-view.md) | The class that helps you deploy a camera view for displaying and processing the video stream. The view also allows for basic UI customization. |

### Auxiliary Classess/Interfaces

| Classes | Description |
| ------- | ----------- |
| [`Rect`](class-rect.md) | The class that stores the rectangle information. |
| [`Region`](class-region.md) | The class that stores the region information. Users can configure region of interest. |
| [`Quadrilateral`](class-quadrilateral.md) | The class that stores the vertex coordinates of the quadrilateral.|
| [`BarcodeResult`](class-barcode-result.md) | The class that stores the barcode results. Barcode result can be acquired from result callback when using video barcode decoding. |
| [`BarcodeLocationResult`](class-barcode-location-result.md) | The class that stores the location result of the detected barcodes. |
| [`DBRRuntimeSettings`](class-dbr-runtime-settings.md) | The class that stores barcode decoding settings. |
| [`TorchButton`](class-torch-button.md) | The class stores the torch button configurations. |
| [`ILicenseVerificationListener`](interface-license-verification-listener.md) | The listener for users to receive license verification message from the license server. |
| [`IBarcodeResultListener`](interface-barcode-result-listener.md) | The listener for users to receive the decoded barcode results. |

### Enumerations

| Enumerations | Description |
| ------------ | ----------- |
| [`EnumBarcodeFormat`](enum-barcode-format.md) | The enumeration stores the first group of barcode formats. |
| [`EnumBarcodeFormat_2`](enum-barcode-format2.md) | The enumeration stores the second group of barcode formats. |
| [`EnumDBRPresetTemplate`](enum-dbr-preset-template.md) | The enumeration stores the preset barcode decoding templates. |

## namespace DCVXamarin.Droid

| Classes | Description |
| ------- | ----------- |
| [`DCVCameraEnhancer`](android-camera-enhancer.md) | Implements IDCVCameraEnhancer on Android. |
| [`DCVBarcodeRader`](android-barcode-reader.md) | Implements IDCVBarcodeReader on Android. |

## namespace DCVXamarin.iOS

| Classes | Description |
| ------- | ----------- |
| [`DCVCameraEnhancer`](ios-camera-enhancer.md) | Implements IDCVCameraEnhancer on iOS. |
| [`DCVBarcodeRader`](ios-barcode-reader.md) | Implements IDCVBarcodeReader on iOS. |
