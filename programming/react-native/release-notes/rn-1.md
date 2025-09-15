---
layout: default-layout
title: Release Notes - React Native - Dynamsoft Capture Vision
description: This is the release notes of Dynamsoft Capture Vision - React Native Edition.
keywords:  Capture Vision, React Native, Release Notes
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: 1.x
---

# Release Notes for React Native SDK - 1.x

## 1.1.16 (08/05/2024)

- Added class `DCVFeedback`. You can use this class to trigger beep sound or vibration.
- Added the following `CameraPositions`
  - `CP_BACK_ULTRA_WIDE`: A ultra-wide-angle back camera that supports macro distant capturing.
  - `CP_BACK_DUAL_WIDE_AUTO`: A back-facing virtual camera that can switch between the wide-angle camera and the ultra-wide-angle camera automatically.

## 1.1.14 (05/16/2024)

### Fixed

- Resolved the compatibility issue for **react-native 0.73.0+**.

## 1.1.13 (05/08/2024)

### New

- Added `enhancedFeatures` to `DCVCameraView` class to enable enhanced features such as auto-zoom, frame filter, etc.

### Fixed

- Resolved TS symbol conflicts.
- Fixed bugs where the app might be freezed when re-opening the camera.

## 1.1.12 (05/24/2023)

- Added [`enableDuplicateFilter`](../api-reference/barcode-reader.md#enableduplicatefilter) to `DCVBarcodeReader` class to get unique result from the result callback.

## 1.1.11 (03/28/2023)

- Fixed a bug that might cause thread blocking on the simulator.

## 1.1.9 (03/14/2023)

- Fixed a symbol conflict bug when using typescript.

## 1.1.8 (03/02/2023)

- Fixed a scan region deviation bug.
- Fixed a bug that parameter [`regionMeasuredByPercentage`](../api-reference/interface-region.md) had no effect when set to `false` or `0`.

## 1.1.7 (10/13/2022)

- Fixed a bug of activity-lifecycle management, which might cause camera not be opened when activity is resumed.

## 1.1.6 (09/28/2022)

- Fixed a bug that camera might not be opened after camera permission is allowed.

## 1.1.5 (09/08/2022)

### New

- Added a new method [`decodeFile`](../api-reference/barcode-reader.md#decodefile) in Barcode Reader module to decode barcodes from an image file.
- Added a new property [`barcodeBytes`](../api-reference/interface-barcode-result.md) in `BarcodeResult` to output the base64 string of the barcode.
- Added a new property [`cameraPosition`](../api-reference/camera-view.md#cameraposition) in `DCVCameraView` class for users to switch between front-facing camera and back-facing camera.
- Added an enumeration [`EnumCameraPosition`](../api-reference/enum-camera-position.md).

### Changes

- Renamed `DynamsoftBarcodeReader` class to [`DCVBarcodeReader`](../api-reference/barcode-reader.md).
- Renamed `DynamsoftCameraView` class to [`DCVCameraView`](../api-reference/camera-view.md).

## 1.1.4 (08/09/2022)

- Fixed a bug that might cause a crash when using the library in React Native 0.69.0+.

## 1.1.3 (08/04/2022)

- Minor changes on `DynamsoftCameraView` class.

## 1.1.2 (07/21/2022)

- Fixed a bug in Barcode Reader module that could cause App Store rejection when Build Options - Enable BitCode is set to Yes for an app.

## 1.1.1 (07/06/2022)

### Fixed

- Fixed a bug that might cause a crash when using the library in React Native 0.69.0+.
- Fixed a bug that [`torchState`](../api-reference/camera-view.md#torchstate) might not be set correctly.

## 1.1.0 (07/01/2022)

### New

- Added a new property [`torchState`](../api-reference/camera-view.md#torchstate) and a new enumeration [`EnumTorchState`](../api-reference/enum-torch-state.md). User can turn on/off the torchlight by changing the value of [`torchState`](../api-reference/camera-view.md#torchstate).
- Added a new property [`torchButton`](../api-reference/camera-view.md#torchbutton) and two new interfaces, [`TorchButton`](../api-reference/interface-torch-button.md) and [`Rect`](../api-reference/interface-rect.md), for users to configure the torch button on the UI.

## 1.0.0 (06/23/2022)

- The first release of DBR React Native SDK.
