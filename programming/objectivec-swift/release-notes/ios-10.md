---
layout: default-layout
title: iOS Release Notes v10.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for iOS SDK v10.x.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for iOS SDK - 10.x

## 10.4.3002 (03/07/2025)

### Changes

- Updated `BarcodeScanner` component. Multi-frame cross verification is enabled by default to prevent misreading.
- Fixed a bug where the `scanRegion` might not effect when configured before the creation of `CameraView`.

## 10.4.3001 (02/11/2025)

### New

- Updated `BarcodeScanner` component to support [multiple barcodes scanning](../user-guide/scanner-multi-barcodes.md).
  - Added a new property [`scanningMode`](../api-reference/barcode-scanner/barcode-scanner-config.md#scanningmode) to the class [`BarcodeScannerConfig`](../api-reference/barcode-scanner/barcode-scanner-config.md) for users to switch between the single barcode scanning mode and multiple barcodes scanning mode.
  - Added a new enumeration class [`DSScanningMode`](../api-reference/barcode-scanner/enum-scanning-mode.md) to specify the scanning mode.
- Added a new property [`isCameraToggleButtonVisible`](../api-reference/barcode-scanner/barcode-scanner-config.md#iscameratogglebuttonvisible) to the class [`BarcodeScannerConfig`](../api-reference/barcode-scanner/barcode-scanner-config.md). Users can use this property to show or hide the camera toggle button.

## 10.4.3000 (01/23/2025)

### Fixed

- Fixed a camera adaptation bug when using the iPad device.

## 10.4.2003 (12/26/2024)

### New

- Added a new component `BarcodeScanner`. Users can quickly set up a barcode scanning app with the built-in UI of `BarcodeScanner`. The following classes are added to use the `BarcodeScanner` component:
  - [`DSBarcodeScannerViewController`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-view-controller.html): The main class of `BarcodeScanner`. It is an activity class that implements barcode decoding features.
  - [`DSBarcodeScannerConfig`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html): The class that provides barcode scanning configurations.
  - [`DSBarcodeScanResult`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scan-result.html): The result class.
  - [`DSResultStatus`]({{ site.dbr_ios_api }}barcode-scanner/enum-result-status.html): An enumeration class that describes the result status.

## 10.4.2002 (12/16/2024)

### Fixed

- Fixed a bug where the app might be blocked by the method `initLicense`.

## 10.4.2001 (11/13/2024)

### Fixed

- Internal changes to prevent crash bugs in barcode decoding.

## 10.4.2000 (10/11/2024)

### Highlights

- Improved the read rate and the speed of the following barcode formats:
  - EAN13
  - DotCode
- Added support for decoding add-on codes (also known as Extension Codes) for UPC-A, UPC-E, EAN-8 and EAN-13 codes.

### Improved

- Improved the read rate and the speed of the following barcode formats:
  - EAN13
  - DotCode
- Updated the error handling logic of `capturing` & `startCapturing` methods. The methods will be able to clearly report where the error occurred if the capturing fails due to a licensing issue.
- Updated the error message of `initLicense` method. The method will return more detailed messages when failed to initialize the license. Warnings will be available if license initialization is successful but a part of the license key is invalid.

### New

- Added internal logics for usage count.
- Added support for decoding add-on barcodes.
- Added new properties to the `DSQRCodeDetails` class
  - `dataMaskPattern`
  - `codewords`
- Added internal logics for usage count.
- Added a new callback method `onRawTextLinesReceived` to the class `DSIntermediateResultReceiver`.
- Added new error codes
  - -10076: The license is initialized successfully but detected invalid content in your key.
  - -30063: [Barcode Reader] No license found.
  - -40103: [Label Recognizer] No license found.
  - -50058: [Document Normalizer] No license found.
  - -90012: [Code Parser] No license found.
- Added a new enumeration member `IntermediateResultUnitTypeRawTextLines` to the enumeration `DSIntermediateResultUnitType`.
- Add a new charge way, `TimeSliceCount`.
- Changed the maximum length of the `deviceFriendlyName` to 255.
- Added to-the-latest overlapping feature. You can use `enableLatestOverlapping` method of `DSMultiFrameResultCrossFilter` class to enable this feature.

### Fixed

- Fixed a bug where the `CharacterModel` is not correctly loaded under macOS operation system.
- Small fixes and tweaks.
- Fixed a crash bug caused by the usage of RegEx.
- Small fixes and tweaks.
- Fixed a bug where `DSCaptureVisionRouter.startCapturing` would erroneously halt the fetching process when its status was running, leading to an unnecessary stop and restart of the fetching operation.
- Fixed a bug where `DSDirectoryFetcher` would prematurely read an image before verifying if the buffer was full, resulting in potential loss of the image that did not make it into the buffer upon calling `stopFetching`.
- Fixed a bug that might cause `GS1DatabarExpandedStacked` barcode unread.

### Changed

- Updated the Enumeration number of `BarcodeFormatAll` to 0xFFFFFFFEFFFFFFFF.
- Updated the internal logic of licensing error message reporting.
- Changed the template loading mode. The library will read all template files under the Templates folder where the DLL file is located.

## 10.2.1101 (07/24/2024)

- Updated signature of license module to prevent rejection of App Store.

## 10.2.1100 (05/15/2024)

### Fixed

- Fixed a bug where `DSOneDCodeDetails` might be nil.

## 10.2.10 (04/16/2024)

### Improved

- Security update for `DynamsoftBarcodeReader` library and other corresponding libraries.
- Supported multiple instances of the class `CaptureVisionRouter`.
- Improved the usage count logic of the concurrent license mode.
- Improved the experience of local cache usage when failing to connect the license server. The renewal of the local cache is optimized as well.
- Improved the barcode decoding performance:
  - Improved the accuracy when decoding OneD & PDF417 barcodes.
  - Improved the readability of dense DataMatrix codes.

### New

- Updated the template system
  - Added `StringLengthRange` for [`TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html).
  - Added Argument `BarcodeFormat` for [`DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html). Currently, you can specify "BF_DATAMATRIX"  or "BF_QR_CODE" for the parameter.
  - Added `ReferenceTaskNameArray` under [`Location.ReferenceObjectFilter`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html#referenceobjectfilter) to filter the reference objects generated by the task name.
  - Added the support of the [`OutputTaskSetting`]({{ site.dcvb_parameters_reference }}output-task-setting/index.html) definition. The following subparameters are available in `OutputTaskSetting` object:
    - `OutputCondition`
    - `TaskResultArray`
    - `TargetROIDefName`
    - `TaskSettingNameArray`
    - `BackwardReferenceOutput`
    - `ReferenceTaskNameArray`
    - `ReferenceResultTypeArray`
    - `Operator`
  - [`Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html#offset) parameter is optimized.
    - Added `ReferenceObjectType` to specify whether the reference object is an atomic object or the whole image.
    - Added `ReferenceXAxis` & `ReferenceYAxis` to define the X & Y axis.
    - Modified `FirstPoint`, `SecondPoint`, `ThirdPoint` & `FourthPoint`. You can specify whether the X or Y coordinate of the point is measured by percentage.
    - Deprecated `ReferenceObjectSize` Type.
- The following classes are migrated from `DynamsoftCore` library to `DynamsoftCaptureVisionRouter` library.
  - [`DSCapturedResult`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result.html)
  - [`DSIntermediateResultReceiver`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
  - [`DSCapturedResultReceiver`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
  - [`DSCapturedResultFilter`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
  - [`DSIntermediateResultManager`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- Added a new call back method [`onShortLinesUnitReceived`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html#onshortlinesunitreceived) to the `DSIntermediateResultReceiver` class.
- Added methods [`pauseCapturing`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#pausecapturing) and [`resumeCapturing`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#resumecapturing). Two new enumeration members, `CS_PAUSED` and `CS_RESUMED`, are added to [`DSCapturedState`]({{ site.dcvb_ios_api }}capture-vision-router/enum/capture-state.html?lang=android) as well.
- Added a new method [`getDecodedBarcodesResult`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result.html) to the [`CapturedResult`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result.html) class to get all the result items with the type `CRIT_BARCODE`.
- Added new methods to the [`DSCandidateBarcodeZonesUnit`]({{ site.dbr_ios_api }}candidate-barcode-zones-unit.html) class to add, remove or set the candidate barcode zones. [`DSCandidateBarcodeZone`]({{ site.dbr_ios_api }}candidate-barcode-zone.html) class is added to store the information of a single candidate barcode zone.
- Added new methods to the [`DSLocalizedBarcodesUnit`]({{ site.dbr_ios_api }}localized-barcodes-unit.html) class to add, remove or set the localized barcode elements.
- Added a new method `setImageData` to the [`DSScaledUpBarcodeImageUnit`]({{ site.dbr_ios_api }}scaled-up-barcode-image-unit.html) class.
- Added new methods to the [`DSDeformationResistedBarcodeImageUnit`]({{ site.dbr_ios_api }}deformation-resisted-barcode-image-unit.html) class to add, remove or set the deformation-resisted barcode. [`DeformationResistedBarcode`]({{ site.dbr_ios_api }}deformation-resisted-barcode.html) class is added to store the deformation-resisted barcode information.
- Added a new method SetLocation to [`DSComplementedBarcodeImageUnit`]({{ site.dbr_ios_api }}complemented-barcode-image-unit.html) class.
- Added new methods to the [`DSDecodedBarcodesUnit`]({{ site.dbr_ios_api }}decoded-barcodes-unit.html) class to set or remove the decoded barcode elements.
- Added the following methods to the [`DSDecodedBarcodesResult`]({{ site.dbr_ios_api }}decoded-barcodes-result.html) class:
  - `retain`
  - `release`.
- Added new constructors to the following classes.
  - [`DSDecodedBarcodeElement`]({{ site.dbr_ios_api }}decoded-barcode-element.html)
  - [`DSLocalizedBarcodeElement`]({{ site.dbr_ios_api }}localized-barcode-element.html)
- Added the following methods to the [`DSDecodeBarcodeElement`]({{ site.dbr_ios_api }}decoded-barcode-element.html) class to modify the basic information of the barcode:
  - `setFormat`
  - `setText`
  - `setBytes`
  - `setConfidence`
- Added a new method `setPossibleFormats` to the [`DSLocalizedBarcodeElement`]({{ site.dbr_ios_api }}localized-barcode-element.html).
- Added the following methods to the [`DSObservationParameters`]({{ site.dcvb_ios_api }}core/intermediate-results/observation-parameters.html) class to specify the `input only` result unit.
  - `setResultUnitTypesOnlyForInput`
  - `getResultUnitTypesOnlyForInput`
- Added the following methods to the [`DSRegionObjectElement`]({{ site.dcvb_ios_api }}core/intermediate-results/region-object-element.html) class to support the intermediate result modification.
  - `setLocation`
  - `clone`
  - `retain`
  - `release`
- Added a new method `replace` to the [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html) class to support the replacement of intermediate result units.
- Added `setImageData` methods to the following classes:
  - [`DSBinaryImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/binary-image-unit.html)
  - [`DSColourImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/colour-image-unit.html)
  - [`DSEnhancedGrayscaleImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
  - [`DSGrayscaleImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/grayscale-image-unit.html)
  - [`DSScaledDownColourImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
  - [`DSTextRemovedBinaryImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/text-removed-binary-image-unit.html)
  - [`DSTextureRemovedBinaryImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
  - [`DSTextureRemovedGrayscaleImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
  - [`DSTransformedGrayscaleImageUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- Added new methods to the [`DSPredetectedRegionsUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/predetected-regions-unit.html) class to add, remove or set the predetected regions.
- Added new methods to the [`DSLineSegmentsUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/line-segments-unit.html) class to add, remove or set the line segments.
- Added new methods to the [`DSTextZonesUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/text-zones-unit.html) class to add, remove or set the text zones. Added a new class CTextZone to store the information of a single text zone.
- Added a new method `setContours` to the [`DSContourUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/contours-unit.html) class.
- Added new methods to the [`DSTextureDetectionResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/texture-detection-result-unit.html) class to set the X & Y spacing.
- Added a new intermediate result unit, [`DSShortLinesUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/short-lines-unit.html), to output the detected short lines. The corresponding enumeration member `IRUT_SHORT_LINES` is added to the `EnumIntermediateResultUnitType`.
- Added the following methods to the [`DSCapturedResultItem`]({{ site.dcvb_ios_api }}core/basic-structures/captured-result-item.html) class
  - `getTargetROIDefName`
  - `getTaskName`
  - `retain`
  - `release`
- Added the following new error codes
  - `DSErrorImageSizeNotMatch`
  - `DSErrorImagePixelFormatNotMatch`
  - `DSErrorSectionLevelResultIrreplaceable`
  - `DSErrorAxisDefinitionIncorrect`
  - `DSErrorTextLineGroupLayoutConflict`
  - `DSErrorTextLineGroupRegexConflict`
  - `DSErrorResultTypeMismatchIrreplaceable`
  - `DSErrorLicenseCacheUsed`
- Added the following methods to the [`DSCapturedResult`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result.html) class.
  - A new override constructor.
  - `retain`
  - `release`
- Added a new supported image pixel format, binary 8 inverted. The corresponding enumeration member is added to the [`DSEnumImagePixelFormat`]({{ site.dcvb_ios_api }}core/enum//image-pixel-format.html?lang=android).
- Added return value for the `retain` method of the `DSIntermediateResultUnit` class. The method will return the pointer of the current [`DSIntermediateResultUnit`]({{ site.dcvb_ios_api }}core/intermediate-results/intermediate-result-unit.html).

### Breaking Changes

- Changed the logic of the [`stopCapturing`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#stopcapturing) method.
  - [`DSCaptureResultReceiver`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) will not receive results after `stopCapturing` is triggered with `waitForRemainingTasks` false.
  - Support stop capturing after the [`pauseCapturing`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#pausecapturing) method is triggered.
- Changed the logic of the `capturedResultItemTypes` setting of [`DSSimplifiedCaptureVisionSettings`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html):
  - If the result item types don't match the specified template, the method [`updateSettings`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#updatesettings) will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types do not match the task configurations in the template".
  - Based on the `capturedResultItemTypes` setting, the irrelevant tasks will be removed from the template.
  - The `capturedResultItemTypes` should include at least one of the `CRIT_BARCODE`, `CRIT_TEXT_LINE`, `CRIT_DETECTED_QUAD`, `CRIT_NORMALIZED_IMAGE`. Otherwise, the method [`updateSettings`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#updatesettings) will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types should contain at least one task result type".
- Refactored the [`DSContour`]({{ site.dcvb_ios_api }}core/basic-structures/contour.html) class. Please view API reference - `Contour` class for more information.

### Fixed

- Fixed a crash bug that might happen when triggering the `setNextImageToReturn` method of the [`DSImageSourceAdapter`]({{ site.dcvb_ios_api }}core/basic-structures/image-source-adapter.html) class.
- Fixed a bug where error messages are not output when parsing the parameter templates.
- Fixed a misreading bug of the PDF417 barcodes on the South Carolina driver’s license.
- Internal changes to prevent crash bugs in barcode decoding.
- Fixed a bug where the capture might be blocked due to the network latency.
- Fixed the bugs of usage count.
  - Count twice for a single PDF417 barcode when a code parser task is implemented on the result.
  - The barcode decoding result might not be uploaded timely.
  - Patchcode might be counted even if there is no Patchcode license item.

## 10.0.21 (12/12/2023)

- Updated the internal package dependencies rules.

## 10.0.20 (10/26/2023)

{%- include release-notes/product-highlight-10.0.0.md -%}

The APIs of Dynamsoft Barcode Reader are comprehensively updated. Please follow the view [upgrade instructions]({{ site.oc }}upgrade.html) to update your code.
