---
layout: default-layout
title: Android Release Notes v9.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for Android SDK v9.x.
keywords: release notes, android, version 9.x,
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/android/release-notes/android-9.html
---

# Release Notes for Android SDK - 9.x

## 9.6.60 (12/23/2025)

This release includes security maintenance updates to ensure continued protection of the product.

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

## 9.6.50 (09/23/2025)

### New

- Supported 16 KB page sizes

## 9.6.40 (03/21/2024)

### Improved

- Updated the security of the `DynamsoftBarcodeReader` library and other corresponding dependent libraries.
- Improved the multi-thread processing logic of concurrent instance licenses.
- Improved the barcode decoding performance:
  - Improved the accuracy when decoding OneD & PDF417 barcodes.
  - Improved the readability of dense DataMatrix codes.

### Changed

- Added a new error code `DM_LICENSE_CACHE_USED`, which is returned when failing to connect to the license server but a valid license cache is available. Error codes  `DM_FAILED_TO_REACH_DLS` and `DM_LICENSE_SYNC_FAILED` are no longer returned in this scenario.

### Fixed

- Fixed crash bugs in the barcode decoding algorithm.
- Fixed a bug where the location of the barcode result(s) might be incorrect.

## 9.6.20 (03/16/2023)

### Fixed

- Fixed a bug where license authorization may fail when the main license server is not available.
- Other small fixes and tweaks.

## 9.6.11 (01/16/2023)

### Fixed

- Fixed a bug that the barcode decoding thread might not restart when [`startScanning`](../api-reference/primary-video.html#startscanning) is triggered shortly after [`stopScanning`](../api-reference/primary-video.html#stopscanning).

## 9.6.10 (01/10/2023)

### Fixed

- Fixed a bug that some OneD barcodes without start & stop characters are not decoded when parameter [`RequireStartStopChars`]({{ site.parameters_reference }}require-start-stop-chars.html) is set to 0.
- Fixed a crash bug by adding protection in algorithm.

### Improved

- Improved the performance of Direct Part Marking (DPM) barcode decoding.
- Improved the performance of GS1 Databar barcode decoding.

## 9.6.0 (12/13/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- **Image orientation** handling is supported by a new feature. With the new feature, you can:
  - Get a **TranformationMatrix** along with the barcode location result.
  - Implement coordinates transformation on the barcode location result with the **TransformationMatrix**.
- **DotCode** decoding is improved by optimizing the localization of DotCodes that are close to one another.

<div align="center">
    <p><img src="../../assets/dotcode-v9.6.png" width="30%" alt="auto-zoom"></p>
</div>

- **EAN8 barcode** decoding is improved by honing the accuracy of localization algorithms.
- **QR code** localizing is improved by reducing the mis-assemble rate of the finder patterns when using the localization mode LM_CONNECTED_BLOCK or LM_SCAN_DIRECTLY, which are designed for speed. The mis-assembling only occurs when there exist dense QR codes on the same image.
- **Mirrored rectangular DataMatrix barcode** is supported by implementing `MirrorMode` when localizing the barcodes.

<div align="center">
    <p><img src="../../assets/rectangle-datamatrix.png" width="30%" alt="auto-zoom"></p>
</div>

- Deformed barcode decoding is improved by extending the supported modes and mode arguments of `DeformationResistingModes`.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added a new method [`setLogConfig`](../api-reference/primary-status-retrieval.html#setlogconfig) so that user can get log information of the algorithm. Enumeration [`EnumLogMode`](../../enumeration/log-mode.html) is added so that users can set whether to save the log information.
- Enabled decoding methods [`decodeFile`](../api-reference/primary-decode.html#decodebuffer), [`decodeFileinMemory`](../api-reference/primary-decode.html#decodefileinmemoryfilebytes) and [`decodeBase64String`](../api-reference/primary-decode.html#decodebase64string) to read EXIF data of the given image so that the library can obtain the orientation information when processing image file.
- Override method [`decodeBuffer`](../api-reference/primary-decode.html#decodebuffer). You can input an [`ImageData`](../api-reference/auxiliary-ImageData.html) object as the barcode decoding parameter. The library can obtain the orientation information from the `ImageData` object.
- Added a new property [`transformationMatrix`](../api-reference/auxiliary-LocalizationResult.html#transformationmatrix) to class `LocalizationResult` so that the library can output a transformation matrix for users to transform the coordinates of the barcode result.
- Added a new method [`setDuplicateForgetTime`](../api-reference/primary-video.html#setduplicateforgettime) to filter out all duplicate barcode results for a period of time when processing video streaming.
- Added new properties [`hasLeftRowIndicator`](../api-reference/auxiliary-PDF417Details.html#hasleftrowindicator) and [`hasRightRowIndicator`](../api-reference/auxiliary-PDF417Details.html#hasrightrowindicator) to class `PDF417Details` to return whether the left or right row indicator of the PDF417 barcode is detected.
- Added a new member [`BF2_ALL`](../../enumeration/barcode-format.html) to enumeration `BarcodeFormatIds_2`.
- Extended the features of <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/deformation-resisting-modes.html?ver=latest" target="_blank">`DeformationResistingModes`</a>:
  - Extended the valid mode arguments of `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` with two new arguments: `GrayscaleEnhancementMode` and `BinarizationMode`.
  - Support mode `DRM_AUTO`.

#### Improved

- Improved the accuracy when processing multiple QR codes.
- Improved the processing speed by excluding incorrectly located barcode zones before decoding.
- Improved the creation, destruction, and acquisition logic of concurrent instances.
- Improved the scan count of duplicate barcodes when the **Charge Way** is **per scan**.
- Improved the accuracy of EAN8 localization result(s).
- Improved the localization of **mirrored DataMatrix barcode** by implementing `MirrorMode`.

#### Fixed

- Fixed a bug that DotCodes might not be decoded when they are densely arranged.
- Fixed a crash bug when trying to output a template which includes customized value for parameterd <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/barcode-text-regex-pattern.html?ver=latest" target="_blank">`BarcodeTextRegEexPattern`</a>.
- Fixed a bug that might cause memory churn when the instance/thread was created frequently.

#### Removed

- Removed `destroy` from class `BarcodeReader`.

## 9.4.0 (11/04/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- DotCode decoding has been improved by optimizing the localization and decoding algorithm.
- Stacked, skewed or perspective distorted OneD barcode decoding has been improved.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added an argument [`IsOneDStacked`]({{ site.parameters_reference }}localization-modes.html#isonedstacked) to `LM_SCAN_DIRECTLY` to process stacked OneD barcodes.
- Added a parameter [`PatchCodeSearchingMargins`]({{ site.parameters_reference }}patchcode-searching-margins.html) to specify the searching area of PatchCode.
- Added the supported data format of [`FormatSpecification.PartitionModes`]({{ site.parameters_reference }}partition-modes.html) to enhance the readability of the parameters. Users can use a list of enumeration names to specify the `PartitionModes`.

#### Improved

- Improved the localization mode `LM_LINES` to better support skewed and perspective OneD barcodes.
- Enhanced tamper resistance of the license keys so that any change to the license string makes it invalid.

#### Deprecated

- Deprecated the attribute `barcodeFormatString_2` of [`TextResult`](../api-reference/auxiliary-TextResult.html), [`ExtendedResult`](../api-reference/auxiliary-ExtendedResult.html) and [`LocalizationResult`](../api-reference/auxiliary-LocalizationResult.html). All the barcode format strings will be returned by the attribute [`barcodeFormatString`](../api-reference/auxiliary-TextResult.html#barcodeformatstring).

## 9.2.10 (06/28/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

- Barcode boundary-seeking algorithm is refactored to improve stability.
- Pharmacode decoding is optimized to improve accuracy.
- The function of device-alias is added to allow users to give each device a readable name. For end-users and administrators, this makes it more friendly to distinguish between devices about license usage statistics.

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added a new method [`setDeviceFriendlyName`]({{ site.android_api }}primary-license.html#setdevicefriendlyname) to set a human-readable name that identifies the device.
- Added a new interface [`ImageSource`]({{ site.android_api }}interface-imagesource.html). It act as an adapter that transfer image data from external resources to the format that can be recognized by the Barcode Reader. The following APIs are available for users to reduce the code complexity when working with [`ImageSource`]({{ site.android_api }}interface-imagesource.html):
  - [`setImageSource`]({{ site.android_api }}primary-video.html#setimagesource): Set [`ImageSource`]({{ site.android_api }}interface-imagesource.html) as the source of image data.
  - [`startScanning`]({{ site.android_api }}primary-video.html#startscanning): Start obaining image from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html) continuously.
  - [`stopScanning`]({{ site.android_api }}primary-video.html#stopscanning): Stop obtaining image from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html).
  - [`TextResultListener`]({{ site.android_api }}interface-textresultcallback.html): The protocol that includes a callback method for users to receive decoded barcode results when decoding from the [`ImageSource`]({{ site.android_api }}interface-imagesource.html).
- Added a new methods [`setMinImageReadingInterval`]({{ site.android_api }}primary-video.html#setminimagereadinginterval) to set a minimum interval between two barcode decoding.

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

- Simplified the license activation steps. Different license activation APIs are integrated into `initLicense` method.
- Added support for **Pharmacode**.
- Added support for **Code 11**, a 1D format.
- Deformation resisting modes `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` are optimized and detached from `DRM_GENERAL`. Users can specify a more effective deformation resisting mode when processing **QRCode** and **DataMatrix codes**.
- Optimized the confidence scoring system for **PDF417 codes**.

### Changelog

#### New

- Added `BF_CODE_11` under enumeration [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) to specify newly supported barcode format, Code 11. The enumeration value of `BF_ONED` and `BF_ALL` are updated as well.
- Added `BF2_PHARMACODE_ONE_TRACK`, `BF2_PHARMACODE_TWO_TRACK` and `BF2_PHARMACODE` under enumeration [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android). to specify newly supported barcode format, Pharmacode.
- Added a new error code [`DBRERR_PHARMACODE_LICENSE_INVALID`]({{ site.mobile_enum }}error-code.html#error-code--10062) which will be returned when the license of Pharmacode is invalid.
- Added `DRM_BROAD_WARP`, `DRM_LOCAL_REFERENCE` and `DRM_DEWRINKLE` under enumeration [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html?lang=android) to apply new deformation resisting modes.
- Added a parameter [`FormatSpecification.VerifyCheckDigit`]({{ site.parameters_reference }}verify-check-digit.html).
- Added new argument [`ConfidenceThreshold`]({{ site.parameters_reference }}localization-modes.html#confidencethreshold) to the `Landroid_apializationModes` mode arguments.
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
