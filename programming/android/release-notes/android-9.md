---
layout: default-layout
title: Dynamsoft Barcode Reader for Android SDK - Release Notes v9.x
description: This is the release notes page of Dynamsoft Barcode Reader for Android SDK v9.x.
keywords: release notes, android, version 9.x,
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/release-notes/android-9.html
---

# Release Notes for Android SDK - 9.x

## 9.2.10 (06/28/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-9.2.0.md -%}

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added a new method [`setDeviceFriendlyName`]({{ site.android_api }}primary-license.html#setdevicefriendlyname) to set a human-readable name that identifies the device.
- Added a new interface [`ImageSource`]({{ site.android_api }}interface-imagesource.html). It acts as an adapter that transfers image data from external resources to a format that can be recognized by the Barcode Reader. The following APIs are available for users to reduce the code complexity when working with [`ImageSource`]({{ site.android_api }}interface-imagesource.html):
  - [`setImageSource`]({{ site.android_api }}primary-video.html#setimagesource): Set [`ImageSource`]({{ site.android_api }}interface-imagesource.html) as the source of image data.
  - [`startScanning`]({{ site.android_api }}primary-video.html#startscanning): Start obaining image from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html) continuously.
  - [`stopScanning`]({{ site.android_api }}primary-video.html#stopscanning): Stop obtaining image from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html).
  - [`TextResultListener`]({{ site.android_api }}interface-textresultcallback.html): The protocol that includes a callback method for users to receive decoded barcode results when decoding from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html).
- Added a new method [`minImageReadingInterval`]({{ site.android_api }}primary-video.html#setminimagereadinginterval) to set the minimum interval between consecutive barcode decoding processes.

## 9.0.2 (05/26/2022)

### New

- Added the following property/Method to iImageData class:
  - [`toBitmap`]({{ site.android_api }}auxiliary-ImageData.html#tobitmap): The method that can convert the ImageData to a Bitmap.
  - [`orientation`]({{ site.android_api }}auxiliary-ImageData.html#orientation): The property that indicates the orientation of the image.

### Changed

- Changed [`getVersion`]({{ site.android_api }}primary-status-retrieval.html#getversion) from a dynamic method to a static method. The format of the return value is changed as well.

### Fixed

- Fixed a bug that `TextResult` might not be returned in `TextResultCallback`

## 9.0.1 (04/20/2022)

### Fixed

- Fixed a bug that might offset the position of highlight overlays on the decoded barcodes when used together with `DynamsoftCameraEnhancer`.

## 9.0.0 (03/22/2022)

### Highlights

{%- include release-notes/product-highlight-9.0.0.md -%}

### Changelog

#### New

- Added `BF_CODE_11` under enumeration [`EnumBarcodeFormat`]({{ site.enumerations }}format-enums.html#barcodeformat) to specify newly supported barcode format, Code 11. The enumeration value of `BF_ONED` and `BF_ALL` are updated as well.
- Added `BF2_PHARMACODE_ONE_TRACK`, `BF2_PHARMACODE_TWO_TRACK` and `BF2_PHARMACODE` under enumeration [`EnumBarcodeFormat_2`]({{ site.enumerations }}format-enums.html#barcodeformat_2). to specify newly supported barcode format, Pharmacode.
- Added a new error code [`DBRERR_PHARMACODE_LICENSE_INVALID`]({{ site.enumerations }}error-code.html#error-code--10062) which will be returned when the license of Pharmacode is invalid.
- Added `DRM_BROAD_WARP`, `DRM_Landroid_apiAL_REFERENCE` and `DRM_DEWRINKLE` under enumeration [`EnumDeformationResistingMode`]({{ site.enumerations }}parameter-mode-enums.html#deformationresistingmode) to apply new deformation resisting modes.
- Added a parameter [`FormatSpecification.VerifyCheckDigit`]({{ site.parameters_reference }}verify-check-digit.html).
- Added new argument [`ConfidenceThreshold`]({{ site.parameters_reference }}landroid_apialization-modes.html#confidencethreshold) to the `Landroid_apializationModes` mode arguments.
- Added static method [`BarcodeReader.initLicense`]({{ site.android_api }}primary-license.html#initlicense) to replace legacy license activation APIs. The new method will support both online and offline licenses.
- Added interface [`DBRLicenseVerificationListener`]({{ site.android_api }}interface-dbrlicenseverificationlistener.html) to get license verification callback when using `BarcodeReader.initLicense`.
- Added interface [`TextResultListener`]({{ site.android_api }}interface-textresultcallback.html).
- Added interface [`IntermediateResultListener`]({{ site.android_api }}interface-intermediateresultcallback.html).
- Added the following image [decoding methods]({{ site.android_api }}primary-decode.html). The parameter `templateName` is not required in the new methods.
  - `BarcodeReader.decodeBuffer`
  - `BarcodeReader.decodeFile`
  - `BarcodeReader.decodeFileInMemory`
  - `BarcodeReader.decodeBase64String`
  - `BarcodeReader.decodeBufferedImage`
  - `BarcodeReader.decodeIntermediateResults`

#### Fixed

- Fixed a bug that might cause a crash when using multiple threads for barcode decoding.

#### Deprecated

- The following license activation APIs are deprecated and will be removed in 10.0 release:
  - Class `DMDLSConnectionParameters`
  - Interface `DBRServerLicenseVerificationListener`
  - Interface `DBRDLSLicenseVerificationListener`
  - Enumeration `EnumDMChargeWay`
  - Enumeration `EnumDMLicenseModule`
  - Enumeration `EnumDMUUIDGenerationMethod`
  - Enumeration `EnumProduct`
  - Method `BarcodeReader.initLicenseFromServer`
  - Method `BarcodeReader.initLicenseFromLicenseContent`
  - Method `BarcodeReader.initLicenseFromDLS`
  - Method `BarcodeReader.outputLicenseToString`

- The image decoding methods with parameter templateName are deprecated
  - `BarcodeReader.decodeBuffer`
  - `BarcodeReader.decodeFile`
  - `BarcodeReader.decodeFileInMemory`
  - `BarcodeReader.decodeBase64String`
  - `BarcodeReader.decodeBufferedImage`
  - `BarcodeReader.decodeIntermediateResults`

- Interface `TextResultCallback` is deprecated.
- Interface `IntermediateResultCallback` is deprecated.

#### Breaking Changes

- Configurations of the preset templates are changed.
  - Changed the configurations of `EnumPresetTemplate.DEFAULT` to `EnumPresetTemplate.VIEDE_SINGLE_BARCODE`.
  - Added template `EnumPresetTemplate.IMAGE_DEFAULT` to store the legacy configurations of `EnumPresetTemplate.DEFAULT`.
- Removed legacy video barcode decoding APIs
  - Class `DCESettingParameters`
  - Class `FrameDecodingParameters`
  - Enumeration `EnumClarityCalculationMethod`
  - Enumeration `EnumClarityFilterMode`
  - Interface `ErrorCallback`
  - Method `BarcodeReader.SetCameraEnhancerParam`
  - Method `BarcodeReader.StartCameraEnhancer`
  - Method `BarcodeReader.StopCameraEnhancer`
  - Method `BarcodeReader.PauseCameraEnhancer`
  - Method `BarcodeReader.ResumeCameraEnhancer`
  - Method `BarcodeReader.startFrameDecoding`
  - Method `BarcodeReader.startFrameDecodingEx`
  - Method `BarcodeReader.appendFrame`
  - Method `BarcodeReader.setErrorCallback`
  - Method `BarcodeReader.stopFrameDecoding`
  - Method `BarcodeReader.initFrameDecodingParameters`
  - Method `BarcodeReader.getLenghtOfFrameQueue`

- Removed the following legacy license activation APIs
  - Interface `DMLTSConnectionParameters`
  - Protocol `DBRLTSLicenseVerificationListener`
  - Method `initLicenseFromLTS`
