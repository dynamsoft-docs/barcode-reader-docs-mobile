---
layout: default-layout
title: Android Release Notes v10.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for Android SDK v10.x.
keywords: release notes, android, version 10.x,
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for Android SDK - 10.x

## 10.4.3002 (03/07/2025)

### Changes

- Updated `BarcodeScanner` component. Multi-frame cross verification is enabled by default to prevent misreading.
- Minor updates for cross-platform development.

## 10.4.3001 (02/11/2025)

### New

- Updated `BarcodeScanner` component to support [multiple barcodes scanning](../user-guide/scanner-multi-barcodes.md).
  - Added a new method [`setScanningMode`](../api-reference/barcode-scanner/barcode-scanner-config.md#setscanningmode) to the class [`BarcodeScannerConfig`](../api-reference/barcode-scanner/barcode-scanner-config.md) for users to switch between the single barcode scanning mode and multiple barcodes scanning mode.
  - Added a new enumeration class [`EnumScanningMode`](../api-reference/barcode-scanner/enum-scanning-mode.md) to specify the scanning mode.
- Added a new method [`setCameraToggleButtonVisible`](../api-reference/barcode-scanner/barcode-scanner-config.md#setcameratogglebuttonvisible) to the class [`BarcodeScannerConfig`](../api-reference/barcode-scanner/barcode-scanner-config.md). Users can use this method to show or hide the camera toggle button.

## 10.4.3000 (01/23/2025)

### Fixed

- Fixed a security issue by rebuilding the affected libraries with enhanced protection mechanisms.

## 10.4.2003 (12/26/2024)

### New

- Added a new component `BarcodeScanner`. Users can quickly set up a barcode scanning app with the built-in UI of `BarcodeScanner`. The following classes are added to use the `BarcodeScanner` component:
  - [`BarcodeScannerActivity`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-activity.html): The main class of `BarcodeScanner`. It is an activity class that implements barcode decoding features.
  - [`BarcodeScannerConfig`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html): The class that provides barcode scanning configurations.
  - [`BarcodeScanResult`]({{ site.dbr_android_api }}barcode-scanner/barcode-scan-result.html): The result class.
  - [`EnumResultStatus`]({{ site.dbr_android_api }}barcode-scanner/enum-result-status.html): An enumeration class that describes the result status.

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
- Added new properties to the `QRCodeDetails` class
  - `getDataMaskPattern`
  - `getCodewords`
- Added internal logics for usage count.
- Added a new callback method `onRawTextLinesReceived` to the class `IntermediateResultReceiver`.
- Added new error codes
  - -10076: The license is initialized successfully but detected invalid content in your key.
  - -30063: [Barcode Reader] No license found.
  - -40103: [Label Recognizer] No license found.
  - -50058: [Document Normalizer] No license found.
  - -90012: [Code Parser] No license found.
- Added a new enumeration member `IRUT_RAW_TEXT_LINES` to the enumeration `IntermediateResultUnitType`.
- Add a new charge way, `TimeSliceCount`.
- Changed the maximum length of the `deviceFriendlyName` to 255.
- Added to-the-latest overlapping feature. You can use `enableLatestOverlapping` method of `MultiFrameResultCrossFilter` class to enable this feature.

### Fixed

- Fixed a bug where the `CharacterModel` is not correctly loaded under macOS operation system.
- Small fixes and tweaks.
- Fixed a crash bug caused by the usage of RegEx.
- Small fixes and tweaks.
- Fixed a bug where `CaptureVisionRouter.startCapturing` would erroneously halt the fetching process when its status was running, leading to an unnecessary stop and restart of the fetching operation.
- Fixed a bug where `DirectoryFetcher` would prematurely read an image before verifying if the buffer was full, resulting in potential loss of the image that did not make it into the buffer upon calling `stopFetching`.
- Fixed a bug that might cause `GS1_DATABAR_EXPANDED_STACKED` barcode unread.

### Changed

- Updated the Enumeration number of `EnumBarcodeFormat.BF_ALL` to 0xFFFFFFFEFFFFFFFF.
- Updated the internal logic of licensing error message reporting.
- Changed the template loading mode. The library will read all template files under the Templates folder where the DLL file is located.

## 10.2.1100 (05/15/2024)

- Added new methods `toJson` & `fromJson` to the [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html) class.

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
- The following classes are migrated from `DynamsoftCore` module to `DynamsoftCaptureVisionRouter` module:
  - [`CapturedResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html)
  - [`IntermediateResultReceiver`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html)
  - [`CapturedResultReceiver`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html)
  - [`CapturedResultFilter`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-filter.html)
  - [`IntermediateResultManager`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html)
- Added a new call back method [`onShortLinesUnitReceived`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/intermediate-result-receiver.html#onshortlinesunitreceived) to the `IntermediateResultReceiver` class.
- Added methods [`pauseCapturing`]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#pausecapturing) and [`resumeCapturing`]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#resumecapturing). Two new enumeration members, `CS_PAUSED` and `CS_RESUMED`, are added to [`CapturedState`]({{ site.dcvb_android_api }}capture-vision-router/enum/capture-state.html?lang=android) as well.
- Added a new method [`getDecodedBarcodesResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html) to the [`CapturedResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html) class to get all the result items with the type `CRIT_BARCODE`.
- Added new methods to the [`CandidateBarcodeZonesUnit`]({{ site.dbr_android_api }}candidate-barcode-zones-unit.html) class to add, remove or set the candidate barcode zones. [`CandidateBarcodeZone`]({{ site.dbr_android_api }}candidate-barcode-zone.html) class is added to store the information of a single candidate barcode zone.
- Added new methods to the [`LocalizedBarcodesUnit`]({{ site.dbr_android_api }}localized-barcodes-unit.html) class to add, remove or set the localized barcode elements.
- Added a new method `setImageData` to the [`ScaledUpBarcodeImageUnit`]({{ site.dbr_android_api }}scaled-up-barcode-image-unit.html) class.
- Added new methods to the [`DeformationResistedBarcodeImageUnit`]({{ site.dbr_android_api }}deformation-resisted-barcode-image-unit.html) class to add, remove or set the deformation-resisted barcode. `DeformationResistedBarcode` class is added to store the deformation-resisted barcode information.
- Added a new method `setLocation` to [`ComplementedBarcodeImageUnit`]({{ site.dbr_android_api }}complemented-barcode-image-unit.html) class.
- Added new methods to the [`DecodedBarcodesUnit`]({{ site.dbr_android_api }}decoded-barcodes-unit.html) class to set or remove the decoded barcode elements.
- Added the following methods to the [`DecodedBarcodesResult`]({{ site.dbr_android_api }}decoded-barcodes-result.html) class:
  - `retain`
  - `release`.
- Added new constructors to the following classes.
  - [`DecodedBarcodeElement`]({{ site.dbr_android_api }}decoded-barcode-element.html)
  - [`LocalizedBarcodeElement`]({{ site.dbr_android_api }}localized-barcode-element.html)
- Added the following methods to the [`DecodeBarcodeElement`]({{ site.dbr_android_api }}decoded-barcode-element.html) class to modify the basic information of the barcode:
  - `setFormat`
  - `setText`
  - `setBytes`
  - `setConfidence`
- Added a new method `setPossibleFormats` to the [`LocalizedBarcodeElement`]({{ site.dbr_android_api }}localized-barcode-element.html).
- Added the following methods to the [`ObservationParameters`]({{ site.dcvb_android_api }}core/intermediate-results/observation-parameters.html) class to specify the `input only` result unit.
  - `setResultUnitTypesOnlyForInput`
  - `getResultUnitTypesOnlyForInput`
- Added the following methods to the [`RegionObjectElement`]({{ site.dcvb_android_api }}core/intermediate-results/region-object-element.html) class to support the intermediate result modification.
  - `setLocation`
  - `clone`
  - `retain`
  - `release`
- Added a new method `replace` to the [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html) class to support the replacement of intermediate result units.
- Added `setImageData` methods to the following classes:
  - [`BinaryImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/binary-image-unit.html)
  - [`ColourImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/colour-image-unit.html)
  - [`EnhancedGrayscaleImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/enhanced-grayscale-image-unit.html)
  - [`GrayscaleImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/grayscale-image-unit.html)
  - [`ScaledDownColourImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/scaled-down-colour-image-unit.html)
  - [`TextRemovedBinaryImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/text-removed-binary-image-unit.html)
  - [`TextureRemovedBinaryImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/texture-removed-binary-image-unit.html)
  - [`TextureRemovedGrayscaleImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/texture-removed-grayscale-image-unit.html)
  - [`TransformedGrayscaleImageUnit`]({{ site.dcvb_android_api }}core/intermediate-results/transformed-grayscale-image-unit.html)
- Added new methods to the [`PredetectedRegionsUnit`]({{ site.dcvb_android_api }}core/intermediate-results/predetected-regions-unit.html) class to add, remove or set the predetected regions.
- Added new methods to the [`LineSegmentsUnit`]({{ site.dcvb_android_api }}core/intermediate-results/line-segments-unit.html) class to add, remove or set the line segments.
- Added new methods to the [`TextZonesUnit`]({{ site.dcvb_android_api }}core/intermediate-results/text-zones-unit.html) class to add, remove or set the text zones. Added a new class `TextZone` to store the information of a single text zone.
- Added a new method `setContours` to the [`ContourUnit`]({{ site.dcvb_android_api }}core/intermediate-results/contours-unit.html) class.
- Added new methods to the [`TextureDetectionResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/texture-detection-result-unit.html) class to set the X & Y spacing.
- Added a new intermediate result unit, [`ShortLinesUnit`]({{ site.dcvb_android_api }}core/intermediate-results/short-lines-unit.html), to output the detected short lines. The corresponding enumeration member `IRUT_SHORT_LINES` is added to the `EnumIntermediateResultUnitType`.
- Added the following methods to the [`CapturedResultItem`]({{ site.dcvb_android_api }}core/basic-structures/captured-result-item.html) class
  - `getTargetROIDefName`
  - `getTaskName`
  - `retain`
  - `release`
- Added the following new error codes
  - `EC_IMAGE_SIZE_NOT_MATCH`
  - `EC_IMAGE_PIXEL_FORMAT_NOT_MATCH`
  - `EC_SECTION_LEVEL_RESULT_IRREPLACEABLE`
  - `EC_AXIS_DEFINITION_INCORRECT`
  - `EC_TEXT_LINE_GROUP_LAYOUT_CONFLICT`
  - `EC_TEXT_LINE_GROUP_REGEX_CONFLICT`
  - `EC_RESULT_TYPE_MISMATCH_IRREPLACEABLE`
  - `EC_LICENSE_CACHE_USED`
- Added the following methods to the [`CapturedResult`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result.html) class.
  - A new override constructor.
  - `retain`
  - `release`
- Added a new supported image pixel format, binary 8 inverted. The corresponding enumeration member is added to the [`EnumImagePixelFormat`]({{ site.dcvb_android_api }}core/enum//image-pixel-format.html?lang=android).
- Added return value for the `retain` method of the `IntermediateResultUnit` class. The method will return the pointer of the current [`IntermediateResultUnit`]({{ site.dcvb_android_api }}core/intermediate-results/intermediate-result-unit.html).

### Breaking Changes

- Changed the logic of the [`stopCapturing`]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#stopcapturing) method.
  - [`CaptureResultReceiver`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html) will not receive results after `stopCapturing` is triggered with `waitForRemainingTasks` false.
  - Support stop capturing after the [`pauseCapturing`]({{ site.dcvb_android_api }}capture-vision-router/multiple-file-processing.html#pausecapturing) method is triggered.
- Changed the logic of the `capturedResultItemTypes` setting of [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html):
  - If the result item types don't match the specified template, the method [`updateSettings`]({{ site.dcvb_android_api }}capture-vision-router/settings.html#updatesettings) will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types do not match the task configurations in the template".
  - Based on the `capturedResultItemTypes` setting, the irrelevant tasks will be removed from the template.
  - The `capturedResultItemTypes` should include at least one of the `CRIT_BARCODE`, `CRIT_TEXT_LINE`, `CRIT_DETECTED_QUAD`, `CRIT_NORMALIZED_IMAGE`. Otherwise, the method [`updateSettings`]({{ site.dcvb_android_api }}capture-vision-router/settings.html#updatesettings) will return the error code `EC_PARAMETER_VALUE_INVALID` with the message "The captured result item types should contain at least one task result type".
- Refactored the [`Contour`]({{ site.dcvb_android_api }}core/basic-structures/contour.html) class. Please view API reference - `Contour` class for more information.

### Fixed

- Fixed a crash bug that might happen when triggering the `setNextImageToReturn` method of the [`ImageSourceAdapter`]({{ site.dcvb_android_api }}core/basic-structures/image-source-adapter.html) class.
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

The APIs of Dynamsoft Barcode Reader are comprehensively updated. Please follow the view [upgrade instructions]({{ site.android }}upgrade.html) to update your code.
