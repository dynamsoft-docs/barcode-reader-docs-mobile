---
layout: default-layout
title: iOS Release Notes v8.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for iOS SDK v8.x.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/release-notes/ios-8.html
---

# Release Notes for iOS SDK - 8.x

## 8.9.3 (03/02/2022)

### Fixed

- Removed the mandatory dependency of `DynamsoftCameraEnhancer`.
- Fixed a bug that might offset the position of highlight overlays on the decoded barcodes when used together with `DynamsoftCameraEnhancer`.

## 8.9.1 (12/28/2021)

- Fixed a bug that might affect the processing speed.

## 8.9.0 (12/16/2021)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- Preset templates are available for users to configure the `PublicRuntimeSettings` parameters. Users can set the template via the method `updateRuntimeSettings` by specifying an `EnumPresetTemplate` member.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added methods [`setCameraEnhancer`]({{ site.oc_api }}primary-video.html#setcameraenhancer) to replace `SetCameraEnhancerPara` and `iDCESettingParameters`. This method will simplify the binding of the Camera Enhancer to the Barcode Reader.
- Added methods [`startScanning`]({{ site.oc_api }}primary-video.html#stopscanning) and [`stopScanning`]({{ site.oc_api }}primary-video.html#stopscanning) to control the start and stop of the video streaming barcode decoding thread. These methods are only active when using the Dynamsoft Camera Enhancer along with the Barcode Reader.
- Overwrited method [`updateRuntimeSettings`]({{ site.oc_api }}primary-parameter-and-runtime-settings-basic.html#updateruntimesettings). Users can specify a member of [`EnumPresetTemplate`]({{ site.mobile_enum }}preset-template.html?lang=objc,swift) in the method to select a preset parameter setting template for barcode decoding.

#### Improved

- Simplified the usage of the different Modes in the `PublicRuntimeSettings` such as `LocalizationModes`, `DeblurModes`, and more. Users no longer must configure the entire Modes array to include the skipped entries as well. For example:
  - In previous versions, when you set the `DeblurModes`:

  ```objc
  settings.deblurModes = @[@(EnumDeblurModeBasedOnLocBin), @(EnumDeblurModeSharpening),@(0),@(0),@(0),@(0), @(0), @(0)];
  ```

  - In v8.9 version:

  ```objc
  settings.deblurModes = @[@(EnumDeblurModeBasedOnLocBin), @(EnumDeblurModeSharpening)];
  ```

#### Fixed

- Fixed a bug that might cause memory leaks.

#### Deprecated

- The following methods/class are deprecated. They are currently available but will be removed in further updates.
    - `SetCameraEnhancerPara`
    - `iDCESettingParameters`

## 8.8.0 (10/19/2021)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- Added a new localization mode `ONED_FAST_SCAN`, which significantly improved the localization speed for 1D barcodes.
- Added the ability to specify barcode width, height, angle to improve the recognition speed if you have advance information about barcodes.
- Optimized the logic of confidence scoring for 2D barcodes. The 2D barcode results with confidence greater than 30 are more accurate.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added xcframework to the install package.
- Added a new `LocalizationModes` item [`LM_ONED_FAST_SCAN`]({{site.parameters_reference}}localization-modes.html#lm_oned_fast_scan), which significantly improved the localization speed for 1D barcodes.

#### Improved

- Improved the confidence calculation algorithm for 2D barcode results. Users can get even more accurate results by configuring the confidence filter.
- Improved the barcode reading speed by applying the localized barcodes filter. The barcodes will be filtered according to the parameters [`BarcodeHeightRangeArray`]({{site.parameters_reference}}barcode-height-range-array.html), [`BarcodeWidthRangeArray`]({{site.parameters_reference}}barcode-width-range-array.html), [`BarcodeAngleRangeArray`]({{site.parameters_reference}}barcode-angle-range-array.html) and [`MinRatioOfBarcodeZoneWidthToHeight`]({{site.parameters_reference}}min-ratio-of-barcode-zone-width-to-height.html).
- Updated the exception message when the full license is invalid or has expired.

#### Breaking Change(s)

- The low confidence barcode results will no longer be returned by default. The default value of parameter [`minResultConfidence`]({{site.parameters_reference}}min-result-confidence.html) is preset to 30, which can filter out the majority of misreading results and keep as many correct results as possible.

#### API Changes

- Removed the class `iTextResultEx`. Merged all `iTextResultEx` properties to [`iTextResult`]({{site.oc_api}}auxiliary-iTextResult.html).
- Removed the method `getEnabledResultVerificationStatus` from the `BarcodeReader` Class.
- Removed the method `getEnabledDuplicateFilterStatus` from the `BarcodeReader` Class.

## 8.6.0 (07/15/2021)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- Improved the confidence calculating algorithm for 1D barcodes. Misreading rate of results with confidence between 30-100 has been significantly reduced.
- Improved the reading speed on clear images by implementing a new deblur mode `DM_BASED_ON_LOC_BIN`.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added more samples.
- Added new API `enableResultVerification`. The barcode decoding results will be verified before output if this feature is enabled. This will highly improve the accuracy of barcode scanning.
- Added new API `enableDuplicateFilter`. The barcode decoding results will be filtered before output if this feature is enabled. The duplicated results will be output only once for every three seconds.
- Added two `DeblurMode` Enumerations, `DM_BASED_ON_LOC_BIN` and `DM_SHARPENING_SMOOTHING`, to support more usage scenarios.
- Added method `initLicenseFromDLS` in `BarcodeReader` class to replace `initLicenseFromLTS`.
- Added class `iDMDLSConnectionParameters` to replace class `iDMLTSConnectionParameters`.
- Added delegate `DMDLSLicenseVerificationDelegate` and callback `DLSLicenseVerificationCallback` to replace `DMLTSLicenseVerificationDelegate` and `LTSLicenseVerificationCallback`.

#### Improved

- Improved the [`confidence`]({{site.oc_api}}auxiliary-iExtendedResult.html#confidence) algorithm for 1D barcode results. Users can get even more accurate results by configuring the `confidence` filter.

### Fixed

- Fixed a bug that `licenseVerificationCallback` not triggered.

## 8.4.0 (06/08/2021)

### New

- Added a new attribute [`isMirrored`]({{site.oc_api}}auxiliary-iTextResult.html#ismirrored) to the `iTextResultEx` class. `isMirrored` returns whether the barcode is mirrored.
- Added a new attribute [`isDPM`]({{site.oc_api}}auxiliary-iTextResult.html#isdpm) to the `iTextResultEx` class. `isDPM` returns whether the barcode is recognized by the DPM mode.
- Added a new argument, `ThresholdCompensation`, to the `BinarizationModes` mode arguments.

### Improved

- Faster recognition speeds when detecting dense QR Codes.
- Improved the performance of boundary identification for DataMatrix codes.

### Deprecated

- `ThreshValueCoefficient` is now deprecated. It still works in this version but could be removed in the near future. We recommend using `ThresholdCompensation` instead.

### Fixed

- Fixed an issue that happens when calling `initLicenseFromLTS` if [`handShakeCode`]({{site.oc_api}}auxiliary-iDMDLSConnectionParameters.html#handshakecode) is not set.
- Replaced the static library with a dynamic library to avoid compatibility issues with other Dynamsoft products or third-party libraries.

## 8.2.1 (05/27/2021)

### New

- [Dynamsoft Camera Enhancer (DCE)]({{site.dce_ios}}) is now available for DBR users to quickly deploy the camera module. We added a new API and a new class to simplify the user operations when using DBR and DCE at the same time.  
- Added a new class, [`iDCESettingParameters`]({{site.oc_api}}auxiliary-iDCESettingParameters.html), and a new API, [`SetCameraEnhancerParam`]({{site.oc_api}}primary-camera.html#setcameraenhancerparam), to enable the parameter transfer between DBR and the DCE. The parameter transferring will improve the focus ability of the camera.

### Improved

- Samples are updated. DCE is handling the camera-related settings in the samples.

## 8.2.0 (03/17/2021)

### New

- Added a new mode argument, `FindAccurateBoundary`, to [`RegionPredetectionModes`]({{ site.parameters_reference }}Region-Predetection-Modes.html) that determines if the SDK attempts to find an accurate boundary when `RegionPredetectionModes` is set to `RPM_GENERAL_HSV_CONTRAST`.
- Added a new an attribute, `organizationID` (string) to `iDMLTSConnectionParameters`. The attribute adds a new layer of security for both full and trial licenses.

### Improved

- Improved both the localization and decoding algorithms for Postal Codes.
- Localization mode `LM_STATISTICS_POSTAL_CODE` will not be added automatically when barcode format postal code is enabled. You can still add `LM_STATISTICS_POSTAL_CODE` manually to get better performance on localizing the postal codes.

### Fixed

- Resolved a bug that infrequently causes the application to crash when decoding a MicroPDF417 barcode.

## 8.1.2 (01/22/2021)

### New

- Added `mode`, `page`, `totalPage` and `parityData` in the `iQRCodeDetails` Class.

### Improved

- Improved the recognition accuracy for GS1 Databar.
- Removed the exception code from `barcodeText` when using a valid trial license.

### Fixed

- Fixed a bug where `barcodeFormatString`, `barcodeFormatString_2`, `regionName` and `documentName` don't have value in the `IRT_TYPED_BARCODE_ZONE` intermediate result.

## 8.1.0 (01/12/2021)

### New

- Added support for MSI Code (Modified Plessey).
- Added a new member `barcodeZoneMinDistanceToImageBorders` in the `iPublicRuntimeSettings` Class to set the minimum distance (in pixels) between barcode zone and image borders. Previously, it is only available in the JSON template. It can be now configured by setting `iPublicRuntimeSettings` -> `barcodeZoneMinDistanceToImageBorders`.
- Added exception error message to `iTextResult` when license initialization fails or decoding authorization fails.

### Improved

- Improved the localization robustness for QR Code.
- Improved the localization for low quality 1D barcodes.
- Improved the deblurring performance and recognition rate for DataMatrix.
- Improved the recognition rate for Aztec code.

### Fixed

- Fixed a bug where Micro PDF417 may not be localized in multiple-barcode scenarios.
- Fixed a bug where the `ExpectedBarcodesCount` and `BarcodeFormat` parameters do not work in the `RegionDefinition`.

## 8.0.0 (11/17/2020)

### New

- (For `IntermediateResult` Advanced Module) Added support for decoding `IntermediateResult`. For example, users with a binarized image could use this function to skip some image preprocessing steps.
- Implemented a new licensing tracking mechanism, License 2.0, which makes it easier for users to track license usage.
- Added a new format control parameter, `BarcodeZoneMinDistanceToImageBorders`, to set the minimum distance (in pixels) between the barcode zone and image borders.
- Added a new format control parameter, `MinRatioOfBarcodeZoneWidthToHeight`, to set the minimum ratio (width/height) of the barcode zone.
- Added a new format control parameter, `BarcodeZoneBarCountRangeArray`, to set the barcode zone's range of bar count for barcode search.
- Added a new argument, `SpatialIndexBlockSize`, for `RPM_GENERAL_RGB_CONTRAST`, `RPM_GENERAL_GRAY_CONTRAST` and `RPM_GENERAL_HSV_CONTRAST`.
- Added a new parameter, `DeblurModes`, so users can use different deblur algorithms for different scenarios. `DeblurModes` has the following enum types: `DirectBinarization`, `ThresholdBinarization`, `GrayEqulization`, `Smoothing`, `Morphing`, `DeepAnalysis` and `Sharpening`.

### Improved

- Improved the localization speed for the `ScanDirectly` mode.
- Improved the localization accuracy for DataMatrix codes with a narrow quiet zone.

### Feature Deprecated

- `DeblurLevel` is now deprecated. It still works in this version but could be removed in the near future. We recommend using `DeblurModes` instead.
