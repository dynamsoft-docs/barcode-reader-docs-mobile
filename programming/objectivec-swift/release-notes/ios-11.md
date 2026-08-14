---
layout: default-layout
title: iOS Release Notes v11.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for iOS SDK v11.x.
keywords: release notes, ios, 
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for iOS SDK - 11.x

## 11.6.2000 (08/14/2026)

### New

- Added support for Micro PDF417-specific decoding mode.

### Fixed

- Fixed several known crash issues.

## 11.6.1000 (07/30/2026)

### Highlights

#### Multi-Threaded Barcode Decoding

- **Get results sooner with parallel processing** - Barcode decoding now uses a breadth-first strategy that decomposes a single DBR Task into one Localization Work and one or more Decoding Works. This improves thread utilization and reduces the chance that a slow `DeblurMode` attempt blocks other faster decoding attempts, helping valid results come back sooner.

#### DataMatrix Color Inversion Detection

- **Handle normal and inverted DataMatrix more efficiently** - Added [`AutoDetectColorInversion`]({{ site.dcvb_parameters_reference }}barcode-format-specification/auto-detect-color-inversion.html) to automatically handle both normal and inverted DataMatrix barcodes. Instead of processing the whole image twice, the SDK applies dual-polarity handling only to localized DataMatrix regions, which makes processing faster in dual-polarity scenarios.

#### Barcode Layout Analysis

- **Decode dense grid barcodes more completely** - Added [`DSLayoutAnalyzer`]({{ site.dcvb_ios_api }}utility/layout-analyzer.html) to organize barcode locations into logical line or matrix layouts and infer unrecognized barcode regions when gaps exist, enabling workflows such as fast first-pass decoding, missing-region inference, and targeted second-pass decoding on dense N*M barcode layouts.

#### Cross-Version License Support

- **Use a single license across SDK versions** - Full License 1.0 keys (starting with "f") that are non-perpetual are no longer version-checked, so the same key can be used across SDK versions without reactivation.

### New

- Added [`AutoDetectColorInversion`]({{ site.dcvb_parameters_reference }}barcode-format-specification/auto-detect-color-inversion.html) parameter for `BarcodeFormatSpecification` to support automatic color-inversion detection for DataMatrix barcodes.

- Added [`DSLayoutAnalyzer`]({{ site.dcvb_ios_api }}utility/layout-analyzer.html) class with [`analyze()`]({{ site.dcvb_ios_api }}utility/layout-analyzer.html#analyze) static method for quadrilateral layout analysis.

- Added [`DSLayoutPattern`]({{ site.dcvb_ios_api }}utility/enum-layout-pattern.html) enumeration with values `DSLayoutPatternUnknown`, `DSLayoutPatternLines`, and `DSLayoutPatternMatrix`.

- Added [`DSLayoutElementSource`]({{ site.dcvb_ios_api }}utility/enum-layout-element-source.html) enumeration with values `DSLayoutElementSourceNone`, `DSLayoutElementSourceInput`, and `DSLayoutElementSourceInferred`.

- Added [`DSMeasureUnit`]({{ site.dcvb_ios_api }}core/enum-measure-unit.html) enumeration with values `DSMeasureUnitPixel` and `DSMeasureUnitPercentage`.

- Added [`DSLayoutAxis`]({{ site.dcvb_ios_api }}utility/layout-axis.html), [`DSLayoutAnalysisParameter`]({{ site.dcvb_ios_api }}utility/layout-analysis-parameter.html), [`DSLayoutElement`]({{ site.dcvb_ios_api }}utility/layout-element.html), and [`DSLayoutAnalysisResult`]({{ site.dcvb_ios_api }}utility/layout-analysis-result.html) for layout analysis configuration and results.

- Added a new `GridBarcodeScanner` sample (with `sample_grid.png`) to demonstrate how to use [`DSLayoutAnalyzer`]({{ site.dcvb_ios_api }}utility/layout-analyzer.html) for barcode grid layout detection and logical row/column mapping.

### Changed

- [`MaxParallelTasks`]({{ site.dcvb_parameters_reference }}capture-vision-template/max-parallel-tasks.html) now controls the total number of Work-level threads in the CVR thread pool. For DBR tasks, each Localization Work and Decoding Work occupies one thread slot. DLR and DDN tasks continue to occupy one thread per task.

- [`set_device_friendly_name()`]({{ site.dcvb_ios_api }}license/license-manager.html#set_device_friendly_name) now enforces parameter constraints: maximum 64 characters, allowed characters are letters (a-z, A-Z), digits (0-9), hyphen (-), underscore (_), and period (.), and must start and end with a letter or digit. Returns [`EC_PARAMETER_VALUE_INVALID`]({{ site.dcvb_ios_api }}core/enum-error-code.html) if constraints are not met.

- Replaced `ONNX` model format with `CoreML` model format, resulting in a smaller package size. Note: barcode localization using neural network models now requires a minimum deployment target of iOS 16.

- Improved the default display behavior of corner adjustment points in `ImageEditorView`. Previously, users had to tap the view before the corner adjustment points became visible.

### Fixed

- Fixed an issue in GS1-Databar AI `17` (YYMMDD) results where the month field could be missing a leading zero.

## 11.4.3000 (07/07/2026)

### Security Updates

- Updated third-party libraries to incorporate the latest security fixes.

### Fixed

- Fixed crash issues that could occur on iOS devices.

## 11.4.1200 (04/02/2026)

### Fixed

- Fixed an issue where downloading deep learning models could fail.
- Fixed an issue where the [`switchCapturingTemplate`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#switchcapturingtemplate) method could fail to load deep learning models.
- Fixed a symbol conflict issue.

## 11.4.1010 (03/16/2026)

### Fixed

- Fixed a bug where `DSBarcodeScannerConfig.resolution` is not available when using Objective-C.

## 11.4.1000 (02/05/2026)

### Highlights

#### AI-Powered Barcode Detection and Decoding

- **PDF417 Localization Model** – Introduces the `PDF417Localization` neural network model for improved detection of PDF417 barcodes, especially under challenging conditions.
- **Code39/ITF Decoding Model** – Adds the `Code39ITFDecoder` model for enhanced decoding of Code 39 and ITF barcodes under blurred or low-resolution conditions.
- **Deblur Models for 2D Barcodes** – Adds the `DataMatrixQRCodeDeblur` and `PDF417Deblur` models provide more effective recovery from motion and focus blur for DataMatrix, QR Code, and PDF417 barcodes.

#### ECI (Extended Channel Interpretation) Support

- **ECI Information Return** – Adds support for retrieving Extended Channel Interpretation (ECI) data from barcodes. The new [`DSECISegment`]({{ site.dbr_ios_api }}eci-segment.html) class, along with [`eciSegments`]({{ site.dbr_ios_api }}barcode-result-item.html#ecisegments) method in [`DSBarcodeResultItem`]({{ site.dbr_ios_api }}barcode-result-item.html) class, enable access to character encoding information embedded in barcodes.
- **ECI-Based Text Interpretation** – Adds support for interpreting ECI segments during barcode decoding, improving compatibility with international character sets.

#### Performance Improvements

- **On-Demand Model Loading** – Implements lazy loading for AI models, reducing initialization time by loading models only when first needed.
- **Smart Model Selection** – Models are now loaded based on configured barcode formats, minimizing memory usage by excluding unused models.
- **Improved Confidence Scoring** – Enhances confidence score calculation for results from neural network models, providing more accurate quality indicators.
- **DPM Barcode Optimization** – Improves recognition rate for Direct Part Marking (DPM) barcodes commonly used in industrial and manufacturing environments.

### New

- Added [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) parameter for filtering barcodes based on aspect ratio constraints.
- Added [`setResultCrossVerificationCriteria`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html#setresultcrossverificationcriteria) and [`getResultCrossVerificationCriteria`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html#getresultcrossverificationcriteria) methods to [`DSMultiFrameResultCrossFilter`]({{ site.dcv_ios_api }}utility/multi-frame-result-cross-filter.html) for configurable multi-frame result verification.
- Added a new resolution [`DSResolutionMax`]({{ site.dce_ios_api }}enum/resolution.html) for capturing photos at maximum resolution (3024*4032).
- Added a new listener [`FocusListener`]({{ site.dce_ios_api }}auxiliary-api/interface-focus-listener.html) for receiving callback when the camera focus is completed. You can register the listener via [`setFocusListener`]({{ site.dce_ios_api }}primary-api/camera-enhancer.html#setfocuslistener) method of `DSCameraEnhancer` class.

### Changed

- Barcode text encoding fallback changed from UTF-8 to ISO-8859-1 when no ECI information is present in the barcode.
- Updated default value of `compensation` parameter in [`DSImageProcessor.convertToBinaryLocal`]({{ site.dcv_ios_api }}utility/image-processor.html#converttobinarylocal) from 0 to 10.
- [`convertToBinaryGlobal`]({{ site.dcv_ios_api }}utility/image-processor.html#converttobinaryglobal) and [`convertToBinaryLocal`]({{ site.dcv_ios_api }}utility/image-processor.html#converttobinarylocal) of `DSImageProcessor` class now support color and binary images as input in addition to grayscale images.

### Removed

- Removed `DataMatrixModuleIsotropic` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.
- Removed `MinRatioOfBarcodeZoneWidthToHeight` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.

### Fixed

- Fixed incorrect coordinate in barcode result when using neural network models with a specified region.
- Fixed crash and hang issues that could occur in certain scenarios.
- Fixed various minor bugs and improved overall stability.

## 11.2.5000 (12/16/2025)

This release includes security maintenance updates to ensure continued protection of the product.
 
### Security Updates
 
- Updated third-party libraries to incorporate the latest security fixes.

## 11.2.3000 (11/05/2025)

### Fixed

- Resolved an issue where `CaptureVisionRouter.startCapturing` could take longer than expected to complete.
- Fixed a performance issue that caused slower continuous decoding when using an online license key.

### Changed

- Updated the data types of the following properties in [`DSPDF417Details`]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html):
  - [`errorCorrectionLevel`]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html#errorcorrectionlevel): from `NSData` to `NSArray<NSNumber>`.
  - [`hasLeftRowIndicator`]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html#hasleftrowindicator): from `NSInteger` to `BOOL`.
  - [`hasRightRowIndicator`]({{ site.dbr_ios_api }}auxiliary-iPDF417Details.html#hasrightrowindicator): from `NSInteger` to `BOOL`.

## 11.2.1000 (10/16/2025)

### 🎉Milestone Release

Version 11.2.1000 introduces a series of AI-driven improvements designed to enhance barcode detection accuracy, processing speed, and configuration flexibility.

This release focuses on practical performance gains for production environments across retail, logistics, and manufacturing workflows.

### ✨ Key Highlights

#### AI-Powered Barcode Detection and Decoding

- New Localization Models – Introduces [`OneDLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) and [`DataMatrixQRCodeLocalization`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html#modelnamearray) neural network models for improved detection of **blurred / low-resolution 1D codes**, or **partially damaged DataMatrix/QR codes**.
- Specialized Decoders – Adds [`EAN13Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) and [`Code128Decoder`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) models optimized for **long-distance** and **motion-blurred** decoding scenarios.
- Redesigned Deblur Model – The [`OneDDeblur`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#modelnamearray) model now provides more effective recovery from **motion and focus blur**.
- Configurable Model Selection – The new `ModelNameArray` parameter supports flexible model loading and fine-grained control for specific barcode types.

#### Precision and Processing Control

- Enhanced Deblur Methods – [`DM_DEEP_ANALYSIS`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#dm_deep_analysis) now includes sub-level control with `OneDGeneral`, `TwoDGeneral`, and `EAN13Enhanced` options.
- Barcode Count Expectation – The new [`ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-format-specification/expected-barcodes-count.html) parameter enables **format-specific quantity control** and **early termination** in fixed-count workflows.
- Improved Region Detection – The new [`RPM_GRAY_CONSISTENCY`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html#rpm_gray_consistency) mode provides more precise region extraction based on **grayscale uniformity** and **local consistency** for document and label processing.

### Performance Highlights

#### Barcode Workflows

- Up to **26.5%** higher read rates under blur conditions with as much as **44%** faster processing.
- Reliable decoding of DataMatrix and QR codes with missing or damaged finder patterns.
- Extended operational range beyond 75 cm for long-distance barcode scanning.

### Developer Notes

- Backward Compatibility – Fully compatible with existing integrations; no code-level changes required for upgrade.
- Configuration Flexibility – Expanded parameter set allows comprehensive model configuration for scenario-specific tuning.
- Production Stability – All new models validated in enterprise environments.

### New

- Added a new method, [`switchCapturingTemplate`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#switchcapturingtemplate), which allows switching templates dynamically during the image processing workflow.
- Added a new method, [`clearDLModelBuffers`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#cleardlmodelbuffers), to release memory by clearing buffered deep learning models.
- Added a new method, [`setGlobalIntraOpNumThreads`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#setglobalintraopnumthreads), to configure the global number of threads used for model execution.
- Added a new button, `cameraToggleButton`, to the `CameraView`, allowing users to switch between the front and back cameras.
The following APIs are provided for configuring the `cameraToggleButton`:
  - [`setCameraToggleButton`]({{ site.dce_ios }}auxiliary-api/dcecameraview.html#setcameratogglebuttonwithframe)
  - [`cameraToggleButtonVisible`]({{ site.dce_ios }}auxiliary-api/dcecameraview.html#cameratogglebuttonvisible)

## 11.0.5200 (08/18/2025)

### Fixed

- Fixed an xcframework signature issue.

## 11.0.5100 (08/05/2025)

### Fixed

- Small fixes and tweaks.

## 11.0.5000 (07/29/2025)

### Changed

- **License Validation Behavior**: Instead of stopping execution immediately on an invalid license module, the library now continues processing and returns results from modules with valid licenses. An error is still reported to indicate the license issue.
- **Default Camera Changed**: To address short-distance focusing issues on Pro Max iPhones, the default camera has been switched to `BackDualWideAuto`, enabling automatic switching between the wide and ultra-wide cameras.

### Fixed

- Fixed various minor bugs and improved overall stability.

## 11.0.3000 (05/15/2025)

### [Highlights](https://www.dynamsoft.com/release-highlights/?product=dbr11.0)

- Workflow Improvements
  - Restructured the parameter control hierarchy at all levels for finer scope definition and more granular process management, with the stage level newly added.
  - Enabled custom combinations and sequences of sections, increasing flexibility and operational customization under specific conditions.

- Deep Learning Integration
  - Improved the reading rate of 1D barcode by introducing a new deblurring deep-learning model.

- Algorithm Enhancements
  - Enabled deduplication at the Region of Interest (ROI) level to consolidate results from multiple tasks.
  - Improved the **CODE_128** and **DataMatrix** DeepAnalysis algorithms for better decoding accuracy and performance.
  - Added support for new barcode types: **CODE_32**, **MATRIX_25**, **KIX**, and **TELEPEN**.

- Engineering Optimizations
  - Unified template-loading logic to reduce I/O overhead.
  - Implemented conversion functionality between `CImageData` and image files, including both on-disk and in-memory files.
