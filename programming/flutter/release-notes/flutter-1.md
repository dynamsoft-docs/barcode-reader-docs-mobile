---
layout: default-layout
title: Dynamsoft Capture Vision - Flutter Release Notes
description: This is the release notes of Dynamsoft Capture Vision - Flutter Edition.
keywords:  Capture Vision, Flutter, Release Notes
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: 1.x
---

# Release Notes for Flutter SDK - 1.x

## 1.4.0 (02/14/2025)

- Updated the Android Gradle Plugin (AGP) of the library to support the latest Flutter version. The lowest supported AGP version is 8.0.

## 1.3.2 (01/02/2025)

- Added a new method setFocus to trigger a auto-focus at the specified point.
- Added the support of the ultra-wide angle camera of iOS devices. Users can specify the CP_BACK_ULTRA_WIDE or CP_BACK_DUAL_WIDE_AUTO via the method selectCamera to use the ultra-wide camera.

## 1.3.1 (07/08/2024)

- Added a new method [`setDeviceFriendlyName`]({{ site.flutter-api }}barcode-reader.html#setdevicefriendlyname) to the class `DCVBarcodeReader` for users to set human readable names for the devices.

## 1.3.0 (04/03/2024)

- Updated the SDK to support Flutter 3. The lowest supported Flutter version is 3.10.0.
- Added a new class [`EnumEnhancedFeatures`]({{ site.flutter-api }}enum-enhanced-features.html) for user to specify the enhanced features of `DynamsoftCameraEnhancer`.
- Added a series of zoom control APIs.
  - [`enableEnhancedFeatures`]({{ site.flutter-api }}camera-enhancer.html#enableenhancedfeatures) to enable the specified enhanced feature(s).
  - [`disableEnhancedFeatures`]({{ site.flutter-api }}camera-enhancer.html#disableenhancedfeatures) to disable the specified enhanced feature(s).
  - [`setZoomFactor`]({{ site.flutter-api }}camera-enhancer.html#setzoomfactor) to set the zoom factor.
  - [`setAutoZoomRange`]({{ site.flutter-api }}camera-enhancer.html#setautozoomrange) to set the auto zoom range.
  - [`getAutoZoomRange`]({{ site.flutter-api }}camera-enhancer.html#getautozoomrange) to get the auto zoom range.
  - [`getMaxZoomFactor`]({{ site.flutter-api }}camera-enhancer.html#getmaxzoomfactor) to get the max zoom factor.

## 1.2.2 (03/17/2023)

### Fixed

- Fixed a crash bug on the devices that do not support 16:9 size resolution.
- Fixed a display bug when the display orientation is landscape.

## 1.2.1 (01/12/2023)

### Improved

* Optimized the internal code to support more usage scenarios.

## 1.2.0 (11/16/2022)

### New

* Extended [`DBRRuntimeSettings`](../api-reference/class-dbr-runtime-settings.md) with more **mode parameters**. You can further optimize the barcode decoding performance of your project with the **mode parameters**:
  * `binarizationModes`
  * `deblurLevel`
  * `deblurModes`
  * `region`
  * `scaleDownThreshold`
  * `scaleUpModes`
  * `textResultOrderModes`
  * `furtherModes`
* Added a new class `FurtherModes` to set the `furtherModes` parameter of `DBRRuntimeSettings`.
* Added new methods `setModeArgument` and `getModeArgument` in class `DCVBarcodeReader`. These two methods give you access to the optional arguments of the **mode parameters**.
* Added enumeration classes to set **mode parameters**.

## 1.1.0 (09/08/2022)

### New

- Added a new method [`decodeFile`](../api-reference/barcode-reader.md#decodefile) in Barcode Reader module to decode barcodes from an image file.
- Added a new method [`enableResultVerification`](../api-reference/barcode-reader.md#enableresultverification) in Barcode Reader module to further improve the accuracy of barcode result.
- Added a new property [`torchButton`](../api-reference/camera-view.md#torchbutton) to `DCVCameraView` class for users to create a torch button on the view.
- Added a new class [`Rect`](../api-reference/class-rect.md).
- Added a new property [`barcodeBytes`](../api-reference/class-barcode-result.md) in `BarcodeResult` to output the byte data of the barcode.
- Added a new property [`minResultConfidence`](../api-reference/class-dbr-runtime-settings.md) in `DBRRuntimeSettings` to filter the barcode results by confidence.
- Added a new property [`minResultTextLength`](../api-reference/class-dbr-runtime-settings.md) in `DBRRuntimeSettings` to filter the barcode results by text length.
- Added [`DCVCameraEnhancer`](../api-reference/camera-enhancer.md) class. Moved camera control APIs from `DCVCameraView` class to `DCVCameraEnhancer` class. Added a new method [`selectCamera`](../api-reference/camera-enhancer.md#selectcamera) in `DCVCameraEnhancer` class for users to switch between front-facing camera and back-facing camera.
- Added an enumeration [`EnumCameraPosition`](../api-reference/enum-camera-position.md).

### Changes

- Renamed `DynamsoftBarcodeReader` class to [`DCVBarcodeReader`](../api-reference/barcode-reader.md).
- Renamed `DynamsoftCameraView` class to [`DCVCameraView`](../api-reference/camera-view.md).
- Users have to call [`DCVCameraEnhancer.open`](../api-reference/camera-enhancer.md#open)/[`DCVCameraEnhancer.close`](../api-reference/camera-enhancer.md#close) manually when the application is **resumed**/**inactive**.

## 1.0.0 (07/12/2022)

- The first release of DBR Flutter SDK.
