---
layout: default-layout
title: Dynamsoft Barcode Reader for iOS SDK - Release Notes v9.x
description: This is the release notes page of Dynamsoft Barcode Reader for iOS SDK v9.x.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/release-notes/ios-9.html
---

# Release Notes for iOS SDK - 9.x

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

#### Fixed

- Fixed a memory leak issue by upgrading SDK compile tool from Xcode 9 to Xcode 13.

#### Deprecated

- Deprecated the attribute `barcodeFormatString_2` of [`TextResult`](../api-reference/auxiliary-TextResult.md), [`ExtendedResult`](../api-reference/auxiliary-ExtendedResult.md) and [`LocalizationResult`](../api-reference/auxiliary-LocalizationResult.md). All the barcode format strings will be returned by the attribute [`barcodeFormatString`](../api-reference/auxiliary-TextResult.md#barcodeformatstring).

## 9.2.13 (09/05/2022)

- Fixed a bug that **NSError** might not be returned when errors occured in the decode methods.

## 9.2.12 (08/02/2022)

- Made a minor change to `iRegionDefinition` class to ensure the library can be used together with `DynamsoftCameraEnhancer` in Xamarin.Forms.

## 9.2.11 (07/11/2022)

### Fixed

- Fixed a bug that could cause App Store rejection when **Build Options - Enable BitCode** is set to **Yes** for an app.

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

- Added a new method [`setDeviceFriendlyName`]({{ site.oc_api }}primary-license.html#setdevicefriendlyname) to set a human-readable name that identifies the device.
- Added a new method [`decodeFileInMemory`]({{ site.oc_api }}primary-decode.html#decodefileinmemory) to decode from the images that are stored in memory.
- Added a new interface [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html). It acts as an adapter that transfers image data from external resources to the format that can be recognized by the Barcode Reader. The following APIs are available for users to reduce the code complexity when working with [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html):
  - [`setImageSource`]({{ site.oc_api }}primary-video.html#setimagesource): Set [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html) as the source of image data.
  - [`startScanning`]({{ site.oc_api }}primary-video.html#startscanning): Start obaining image from the [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html) continuously.
  - [`stopScanning`]({{ site.oc_api }}primary-video.html#stopscanning): Stop obtaining image from the [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html).
  - [`TextResultListener`]({{ site.oc_api }}protocol-dbrtextresultdelegate.html): The protocol that includes a callback method for users to receive decoded barcode results when decoding from the [`ImageSource`]({{ site.oc_api }}protocol-imagesource.html).
- Added a new method [`minImageReadingInterval`]({{ site.oc_api }}primary-video.html#minimagereadinginterval) to set the minimum interval between consecutive barcode decoding processes.

## 9.0.2 (05/26/2022)

### New

- Added the following property/Method to iImageData class:
  - [`toUIImage`]({{ site.oc_api }}auxiliary-iImageData.html#touiimage): The method that can convert the iImageData to an UIImage.
  - [`orientation`]({{ site.oc_api }}auxiliary-iImageData.html#orientation): The property that indicates the orientation of the image.

### Changed

- Changed [`getVersion`]({{ site.oc_api }}primary-status-retrieval.html#getversion) from a dynamic method to a static method. The format of the return value is changed as well.

### Fixed

- Fixed a bug that might cause memory leak.

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

- Added `EnumBarcodeFormatCODE11` under enumeration [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) to specify newly supported barcode format, Code 11. The enumeration value of `EnumBarcodeFormatONED` and `EnumBarcodeFormatALL` are updated as well.
- Added `EnumBarcodeFormat2PHARMACODEONETRACK`, `EnumBarcodeFormat2PHARMACODETWOTRACK` and `EnumBarcodeFormat2PHARMACODE` under enumeration [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) to specify newly supported barcode format, Pharmacode.
- Added a new error code [`DBRERR_PHARMACODE_LICENSE_INVALID`]({{ site.mobile_enum }}error-code.html#error-code--10062) which will be returned when the license of Pharmacode is invalid.
- Added `EnumDeformationResistingModeBroadWarp`, `EnumDeformationResistingModeLocalReference` and `EnumDeformationResistingModeDewrinkle` under enumeration [`EnumDeformationResistingMode`]({{ site.mobile_enum }}deformation-resisting-mode.html) to apply new deformation resisting modes.
- Added a parameter [`FormatSpecification.VerifyCheckDigit`]({{ site.parameters_reference }}verify-check-digit.html).
- Added new argument [`ConfidenceThreshold`]({{ site.parameters_reference }}localization-modes.html#confidencethreshold) to the `LocalizationModes` mode arguments.
- Added static method [`DynamsoftBarcodeReader.initLicense`]({{ site.oc_api }}primary-license.html#initlicense) to replace legacy license activation APIs.
- Added protocol [`DBRLicenseVerificationListener`]({{ site.oc_api }}protocol-dmdlslicenseverificationdelegate.html) to get license verification callback when using `DynamsoftBarcodeReader.initLicense`.
- Added protocol [`DBRTextResultListener`]({{ site.oc_api }}protocol-dbrtextresultdelegate.html).
- Added protocol [`DBRIntermediateResultListener`]({{ site.oc_api }}protocol-dbrintermediateresultdelegate.html).
- Added the following image [decoding methods]({{ site.oc_api }}primary-decode.html). The parameter `templateName` is not required in the new methods.
  - `DynamsoftBarcodeReader.decodeBuffer`
  - `DynamsoftBarcodeReader.decodeImage`
  - `DynamsoftBarcodeReader.decodeFileWithName`
  - `DynamsoftBarcodeReader.decodeBase64`
  - `DynamsoftBarcodeReader.decodeIntermediateResult`

#### Fixed

- Fixed a bug that might cause a crash when using multiple threads for barcode decoding.

#### Deprecated

- The following license activation APIs are deprecated:
  - Interface `iDMDLSConnectionParameters`
  - Protocol `DBRServerLicenseVerificationDelegate`
  - Protocol `DMDLSLicenseVerificationDelegate`
  - Enumeration `EnumDMChargeWay`
  - Enumeration `EnumDMLicenseModule`
  - Enumeration `EnumDMUUIDGenerationMethod`
  - Enumeration `EnumProduct`
  - Method `DynamsoftBarcodeReader.initLicenseFromServer`
  - Method `DynamsoftBarcodeReader.initLicenseFromDLS`
  - Method `DynamsoftBarcodeReader.outputLicenseToString`

- The image decoding methods with parameter templateName are deprecated
  - `DynamsoftBarcodeReader.decodeIntermediateResult`
  - `DynamsoftBarcodeReader.decodeImage`
  - `DynamsoftBarcodeReader.decodeFileWithName`
  - `DynamsoftBarcodeReader.decodeBase64`
  - `DynamsoftBarcodeReader.decodeBuffer`

- `DBRTextResultDelegate` is deprecated.
- `DBRIntermediateResultListener` is deprecated.

#### Breaking Changes

- Configurations of the preset templates are changed.
  - Changed the configurations of `EnumPresetTemplate.default` to `EnumPresetTemplate.videoSingleBarcode`.
  - Added template `EnumPresetTemplate.imageDefault` to store the legacy configurations of `EnumPresetTemplate.default`.
- Updated Swift APIs
  - The following method names are changed:
    - `DynamsoftBarcodeReader.updateRuntimeSettings`(with parameter `iPublicRuntimeSettings`)
    - `DynamsoftBarcodeReader.decodeIntermediateResult`
    - `DynamsoftBarcodeReader.decodeImage`
    - `DynamsoftBarcodeReader.decodeFileWithName`
    - `DynamsoftBarcodeReader.initRuntimeSettingsWithFile`
    - `DynamsoftBarcodeReader.initRuntimeSettingsWithString`
    - `DynamsoftBarcodeReader.appendTplFileToRuntimeSettings`
    - `DynamsoftBarcodeReader.appendTplStringToRuntimeSettings`
    - `DynamsoftBarcodeReader.outputSettingsToString`
    - `DynamsoftBarcodeReader.outputSettingsToFile`
    - Enumeration members of `EnumTerminatePhase`
  - The following methods will signal errors by throw exceptions
    - `DynamsoftBarcodeReader.decodeIntermediateResult`
    - `DynamsoftBarcodeReader.decodeImage`
    - `DynamsoftBarcodeReader.decodeFileWithName`
    - `DynamsoftBarcodeReader.decodeBase64`
    - `DynamsoftBarcodeReader.decodeBuffer`
    - `DynamsoftBarcodeReader.getIntermediateResult`
    - `DynamsoftBarcodeReader.createIntermediateResult`
    - `DynamsoftBarcodeReader.outputLicenseToString`
    - `DynamsoftBarcodeReader.outputSettingsToString`
    - `DynamsoftBarcodeReader.allParameterTemplateNames`
    - `DynamsoftBarcodeReader.getModeArgument`
    - `DynamsoftBarcodeReader.getRuntimeSettings`
  - The following methods will return an BOOL value
    - `DynamsoftBarcodeReader.updateRuntimeSettings`
    - `DynamsoftBarcodeReader.setModeArgument`
    - `DynamsoftBarcodeReader.resetRuntimeSettings`
    - `DynamsoftBarcodeReader.initRuntimeSettingsWithFile`
    - `DynamsoftBarcodeReader.initRuntimeSettingsWithString`
    - `DynamsoftBarcodeReader.appendTplFileToRuntimeSettings`
    - `DynamsoftBarcodeReader.appendTplStringToRuntimeSettings`
    - `DynamsoftBarcodeReader.outputSettingsToFile`

- Removed the following legacy video barcode decoding APIs
  - Interface `iDCESettingParameters`
  - Interface `iFrameDecodingParameters`
  - Enumeration `EnumClarityCalculationMethod`
  - Enumeration `EnumClarityFilterMode`
  - Protocol `DBRErrorDelegate`
  - Method `DynamsoftBarcodeReader.setCameraEnhancerParam`
  - Method `DynamsoftBarcodeReader.startFrameDecoding`
  - Method `DynamsoftBarcodeReader.startFrameDecodingEx`
  - Method `DynamsoftBarcodeReader.appendFrame`
  - Method `DynamsoftBarcodeReader.setDBRErrorDelegate`
  - Method `DynamsoftBarcodeReader.stopFrameDecoding`
  - Method `DynamsoftBarcodeReader.getFrameDecodingParameters`
  - Method `DynamsoftBarcodeReader.getLenghtOfFrameQueue`

- Removed the following legacy license activation APIs
  - Interface `iDMLTSConnectionParameters`
  - Protocol `DMLTSLicenseVerificationDelegate`
  - Method `DynamsoftBarcodeReader.initLicenseFromLTS`
  - Property `DynamsoftBarcodeReader.license`
