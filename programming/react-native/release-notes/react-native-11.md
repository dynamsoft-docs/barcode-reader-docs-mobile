---
layout: default-layout
title: React Native Release Notes - Dynamsoft Barcode Reader React Native SDK
description: This is the release notes page of Dynamsoft Barcode Reader for React Native SDK.
keywords: release notes, React Native, barcode reader
needAutoGenerateSidebar: false
breadcrumbText: Release Notes
---

# Dynamsoft Barcode Reader React Native SDK - Release Notes

## 11.4.1200 (04/22/2026)

### Improved

- Updated camera lifecycle management code to improve stability.

### Fixed

- Fixed an issue where downloading deep learning models could fail.
- Fixed an issue where the [`switchCapturingTemplate`]({{ site.dcv_react_native_api }}capture-vision-router/capture-vision-router.html#switchcapturingtemplate) method could fail to load deep learning models.
- Fixed an incorrect nullable NSNumber parameter definition in `setCameraView`.

## 11.4.1100 (03/26/2026)

### Fixed

- Fixed a symbol conflict issue.
- Added new methods to class `LicenseManager`:
  - [`getDeviceUUID`]({{ site.dcv_react_native_api }}license/license-manager.html#getdeviceuuid)
  - [`setDeviceFriendlyName`]({{ site.dcv_react_native_api }}license/license-manager.html#setdevicefriendlyname)

## 11.4.1010 (03/19/2026)

### Highlights

#### AI-Powered Barcode Detection and Decoding

- **PDF417 Localization Model** – Introduces the `PDF417Localization` neural network model for improved detection of PDF417 barcodes, especially under challenging conditions.
- **Code39/ITF Decoding Model** – Adds the `Code39ITFDecoder` model for enhanced decoding of Code 39 and ITF barcodes under blurred or low-resolution conditions.
- **Deblur Models for 2D Barcodes** – Adds the `DataMatrixQRCodeDeblur` and `PDF417Deblur` models provide more effective recovery from motion and focus blur for DataMatrix, QR Code, and PDF417 barcodes.

#### ECI (Extended Channel Interpretation) Support

- **ECI Information Return** – Adds support for retrieving Extended Channel Interpretation (ECI) data from barcodes. The new [`ECISegment`]({{ site.dbr_react_native_api }}barcode-reader/eci-segment.html) class, along with [`eciSegments`]({{ site.dbr_react_native_api }}barcode-reader/barcode-result-item.html#ecisegments) property in [`BarcodeResultItem`]({{ site.dbr_react_native_api }}barcode-reader/barcode-result-item.html) class, enable access to character encoding information embedded in barcodes.
- **ECI-Based Text Interpretation** – Adds support for interpreting ECI segments during barcode decoding, improving compatibility with international character sets.

#### Performance Improvements

- **On-Demand Model Loading** – Implements lazy loading for AI models, reducing initialization time by loading models only when first needed.
- **Smart Model Selection** – Models are now loaded based on configured barcode formats, minimizing memory usage by excluding unused models.
- **Improved Confidence Scoring** – Enhances confidence score calculation for results from neural network models, providing more accurate quality indicators.
- **DPM Barcode Optimization** – Improves recognition rate for Direct Part Marking (DPM) barcodes commonly used in industrial and manufacturing environments.

### New

- Added [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) parameter for filtering barcodes based on aspect ratio constraints.
- Added [`setResultCrossVerificationCriteria`]({{ site.dcv_react_native_api }}utility/multi-frame-cross-filter.html#setresultcrossverificationcriteria) and [`getResultCrossVerificationCriteria`]({{ site.dcv_react_native_api }}utility/multi-frame-cross-filter.html#getresultcrossverificationcriteria) methods to [`MultiFrameResultCrossFilter`]({{ site.dcv_react_native_api }}utility/multi-frame-cross-filter.html) for configurable multi-frame result verification.
- Added a new resolution [`RESOLUTION_MAX`]({{ site.dce_react_native_api }}enum/resolution.html) for capturing photos at maximum resolution (3024*4032).

### Changed

- Barcode text encoding fallback changed from UTF-8 to ISO-8859-1 when no ECI information is present in the barcode.
- Updated default value of `compensation` parameter in [`ImageProcessor.convertToBinaryLocal`]({{ site.dcv_react_native_api }}utility/image-processor.html#converttobinarylocal) from 0 to 10.
- [`convertToBinaryGlobal`]({{ site.dcv_react_native_api }}utility/image-processor.html#converttobinaryglobal) and [`convertToBinaryLocal`]({{ site.dcv_react_native_api }}utility/image-processor.html#converttobinarylocal) of `ImageProcessor` class now support color and binary images as input in addition to grayscale images.

### Removed

- Removed `DataMatrixModuleIsotropic` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.
- Removed `MinRatioOfBarcodeZoneWidthToHeight` parameter – use [`BarcodeZoneWidthToHeightRatioRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-width-to-height-ratio-range-array.html) instead.

### Fixed

- Fixed incorrect coordinate in barcode result when using neural network models with a specified region.
- Fixed crash and hang issues that could occur in certain scenarios.
- Fixed various minor bugs and improved overall stability.

## 11.2.5002 (01/22/2026)

### Fixed

- Fixed a crash issue caused by lifecycle management code.

## 11.2.5000 (12/18/2025)
 
This release includes security maintenance updates to ensure continued protection of the product.
 
### Security Updates
 
- Updated third-party libraries to incorporate the latest security fixes.

## 11.2.3000 (12/04/2025)

### 🎉Milestone Release

Version 11.2.3000 introduces a series of AI-driven improvements designed to enhance barcode detection accuracy, processing speed, and configuration flexibility.

This release focuses on practical performance gains for production environments across retail, logistics, manufacturing, and identity verification workflows.

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

- Added a new method, [`switchCapturingTemplate`]({{ site.dcv_react_native_api }}capture-vision-router/capture-vision-router.html#switchcapturingtemplate), which allows switching templates dynamically during the image processing workflow.
- Added a new method, [`clearDLModelBuffers`]({{ site.dcv_react_native_api }}capture-vision-router/capture-vision-router.html#cleardlmodelbuffers), to release memory by clearing buffered deep learning models.
- Added a new method, [`setGlobalIntraOpNumThreads`]({{ site.dcv_react_native_api }}capture-vision-router/capture-vision-router.html#setglobalintraopnumthreads), to configure the global number of threads used for model execution.
- Added a new button, `cameraToggleButton`, to the `CameraView`, allowing users to switch between the front and back cameras.
The following APIs are provided for configuring the `cameraToggleButton`:
  - [`cameraToggleButton`]({{ site.dce_react_native_api }}camera-view.html#cameratogglebutton)
  - [`cameraToggleButtonVisible`]({{ site.dce_react_native_api }}camera-view.html#cameratogglebuttonvisible)
- Added new methods to class `ImageIO` for reading and saving images:
  - [`readFromMemory`]({{ site.dcv_react_native_api }}utility/image-io.html#readfrommemory)
  - [`saveToMemory`]({{ site.dcv_react_native_api }}utility/image-io.html#savetomemory)
- Added a new method [`cropAndDeskewImage`]({{ site.dcv_react_native_api }}utility/image-processor.html#cropanddeskewimage) to class `ImageProcessor` for cropping & deskewing images.

## 11.0.5200 (08/18/2025)

### Fixed

- Fixed an xcframework signature issue.

## 11.0.5100 (08/12/2025)

### Fixed

- Small fixes and tweaks.

## 11.0.3100 (06/17/2025)

### [Highlights](https://www.dynamsoft.com/release-highlights/?product=dbr11.0)

- Workflow Improvements
  - Restructured the parameter control hierarchy at all levels for finer scope definition and more granular process management, with the stage level newly added.
  - Enabled custom combinations and sequences of sections, increasing flexibility and operational customization under specific conditions.
  
- Deep Learning Integration
  - Improved the reading rate of 1D barcode by introducing a new deblurring deep-learning model.

- Algorithm Enhancements
  - Enabled deduplication at the Region of Interest (ROI) level to consolidate results from multiple tasks.
  - Improved the CODE_128 and DataMatrix DeepAnalysis algorithms for better decoding accuracy and performance.
  - Added support for new barcode types: CODE_32, MATRIX_25, KIX, and TELEPEN.
  - Added GS1 Application Identifiers (AI) support for improved code parsing capabilities.

- Engineering Optimizations
  - Unified template-loading logic to reduce I/O overhead.
  - Implemented conversion functionality between `ImageData` and image files, including both on-disk and in-memory files.
