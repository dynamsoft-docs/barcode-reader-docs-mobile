---
layout: default-layout
title: iOS Release Notes v9.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for iOS SDK v9.x.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
permalink: /programming/objectivec-swift/release-notes/ios-9.html
---

# Release Notes for iOS SDK - 9.x

## 9.6.60 (12/23/2025)

This release includes security maintenance updates to ensure continued protection of the product.

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

## 9.6.40 (03/21/2024)

### Improved

- Updated the security of the `DynamsoftBarcodeReader` library and other corresponding dependent libraries.
- Improved the multi-thread processing logic of concurrent instance licenses.
- Improved the barcode decoding performance:
  - Improved the accuracy when decoding OneD & PDF417 barcodes.
  - Improved the readability of dense DataMatrix codes.

### Changed

- Added a new error code `EnumErrorCode_LICENSE_CACHE_USED`, which is returned when failing to connect to the license server but a valid license cache is available. Error codes  `EnumErrorCode_FAILED_TO_REACH_DLS` and `EnumErrorCode_LICENSE_SYNC_FAILED` are no longer returned in this scenario.

### Fixed

- Fixed crash bugs in the barcode decoding algorithm.
- Fixed a bug where the location of the barcode result(s) might be incorrect.

## 9.6.21 (03/27/2023)

### Fixed

- Fixed a bug that might cause thread blocking on the simulator.

## 9.6.20 (03/16/2023)

### Fixed

- Fixed a bug where license authorization may fail when the main license server is not available.
- Other small fixes and tweaks.

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

- Added a new method [`setLogConfig`](../api-reference/primary-status-retrieval.html#setlogconfig) so that users can set whether to save the log to a file and where the log file will be saved. Enumeration [`EnumLogMode`](../../enumeration/log-mode.html) is added so that users can set whether to save the log information.
- Enabled decoding methods [`decodeFileWithName`](../api-reference/primary-decode.html#decodefilewithname), [`decodeFileinMemory`](../api-reference/primary-decode.html#decodefileinmemory) and [`decodeBase64`](../api-reference/primary-decode.html#decodebase64) to read EXIF data of the given image so that the library can obtain the orientation information when processing image file.
- Enabled decoding method [`decodeImage`](../api-reference/primary-decode.html#decodeimage) to read orientation information from `UIImage`.
- Override method [`decodeBuffer`](../api-reference/primary-decode.html#decodebuffer). You can input an [`iImageData`](../api-reference/auxiliary-iImageData.html) object as the barcode decoding parameter. The library can obtain the orientation information from the `iImageData` object.
- Added a new property [`transformationMatrix`](../api-reference/auxiliary-iLocalizationResult.html#transformationmatrix) to class `iLocalizationResult` so that the library can output a transformation matrix for users to transform the coordinates of the barcode result.
- Added a new property [`duplicateForgetTime`](../api-reference/primary-video.html#duplicateforgettime) to filter out all duplicate barcode results for a period of time when processing video streaming.
- Added new properties [`hasLeftRowIndicator`](../api-reference/auxiliary-iPDF417Details.html#hasleftrowindicator) and [`hasRightRowIndicator`](../api-reference/auxiliary-iPDF417Details.html#hasrightrowindicator) to class `iPDF417Details` to return whether the left or right row indicator of the PDF417 barcode is detected.
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

#### Changed

- Method [`toUIImage`](../api-reference/auxiliary-iImageData.html#touiimage) in class `iImageData` will rotate the image physically according the `orientation` property.

#### Fixed

- Fixed a bug that DotCodes might not be decoded when they are densely arranged.
- Fixed a crash bug when trying to output a template which includes customized value for parameterd <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/barcode-text-regex-pattern.html?ver=latest" target="_blank">`BarcodeTextRegEexPattern`</a>.

#### Removed

- Removed `dispose` from class `BarcodeReader`.

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

- Deprecated the attribute `barcodeFormatString_2` of [`TextResult`](../api-reference/auxiliary-iTextResult.html), [`ExtendedResult`](../api-reference/auxiliary-iExtendedResult.html) and [`LocalizationResult`](../api-reference/auxiliary-iLocalizationResult.html). All the barcode format strings will be returned by the attribute [`barcodeFormatString`](../api-reference/auxiliary-iTextResult.html#barcodeformatstring).

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
