---
layout: default-layout
title: MAUI Release Notes v11.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for MAUI SDK v11.x.
keywords: release notes, android, version 11.x,
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for MAUI SDK - 11.x

## 11.2.5000 (12/18/2025)
 
This release includes security maintenance updates to ensure continued protection of the product.
 
### Security Updates
 
- Updated third-party libraries to incorporate the latest security fixes.

## 11.2.3000 (11/20/2025)

### 🎉Milestone Release

Version 11.2.3000 introduces a series of AI-driven improvements designed to enhance barcode detection accuracy, processing speed, and configuration flexibility.

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

#### Document Workflows

- Improved performance in live video capture environments.
- Consistent document quality through clarity-based frame evaluation.
- Faster MRZ processing for high-throughput identity verification

### Developer Notes

- Backward Compatibility – Fully compatible with existing integrations; no code-level changes required for upgrade.
- Configuration Flexibility – Expanded parameter set allows comprehensive model configuration for scenario-specific tuning.
- Production Stability – All new models validated in enterprise environments.

### New

- Added a new method, [`SwitchCapturingTemplate`]({{ site.dcv_maui_api }}capture-vision-router/multiple-file-processing.html#switchcapturingtemplate), which allows switching templates dynamically during the image processing workflow.
- Added a new method, [`ClearDLModelBuffers`]({{ site.dcv_maui_api }}capture-vision-router/settings.html#cleardlmodelbuffers), to release memory by clearing buffered deep learning models.
- Added a new method, [`SetGlobalIntraOpNumThreads`]({{ site.dcv_maui_api }}capture-vision-router/settings.html#setglobalintraopnumthreads), to configure the global number of threads used for model execution.
- Added a new method, [`TakePhoto`]({{ site.dce_maui_api }}camera-enhancer.html#takephoto) for capturing photos.
- Added a new button, `CameraToggleButton`, to the `CameraView`, allowing users to switch between the front and back cameras.
The following APIs are provided for configuring the `CameraToggleButton`:
  - [`CameraToggleButton`]({{ site.dce_maui_api }}camera-view.html#cameratogglebutton)
  - [`CameraToggleButtonVisible`]({{ site.dce_maui_api }}camera-view.html#cameratogglebuttonvisible)
- Added new methods to class `ImageIO` for reading and saving images:
  - [`ReadFromMemory`]({{ site.dcv_maui_api }}utility/image-io.html#readfrommemory)
  - [`SaveToMemory`]({{ site.dcv_maui_api }}utility/image-io.html#savetomemory)
- Added new methods to class `ImageProcessor` for cropping images:
  - [`CropAndDeskewImage(imageData,quadrilateral,dstWidth,dstHeight,padding)`]({{ site.dcv_maui_api }}utility/image-processor.html#cropanddeskewimageimagedataquadrilateraldstwidthdstheightpaddingerrorcode)
  - [`CropAndDeskewImage(imageData,quadrilateral)`]({{ site.dcv_maui_api }}utility/image-processor.html#cropanddeskewimageimagedataquadrilateral)


## 11.0.5200 (08/18/2025)

### Fixed

- Fixed an xcframework signature issue.

## 11.0.5100 (08/12/2025)

### Fixed

- Small fixes and tweaks.

## 11.0.3100 (05/30/2025)

### [Highlights](https://www.dynamsoft.com/release-highlights/?product=dcv3.0)

- Workflow Improvements
  - Restructured the parameter control hierarchy at all levels for finer scope definition and more granular process management, with the stage level newly added.
  - Enabled custom combinations and sequences of sections, increasing flexibility and operational customization under specific conditions.
  - Redesigned document normalization sections to better accommodate diverse document processing operations.
  
- Deep Learning Integration
  - Improved the reading rate of 1D barcode by introducing a new deblurring deep-learning model.
  - Enhanced text recognition capabilities with deep learning-based text-line recognition.

- Algorithm Enhancements
  - Enabled deduplication at the Region of Interest (ROI) level to consolidate results from multiple tasks.
  - Enhanced the text recognition workflow by integrating improved multi-step recognition processes and validation methods.
  - Improved the CODE_128 and DataMatrix DeepAnalysis algorithms for better decoding accuracy and performance.
  - Added support for new barcode types: CODE_32, MATRIX_25, KIX, and TELEPEN.
  - Added GS1 Application Identifiers (AI) support for improved code parsing capabilities.

- Engineering Optimizations
  - Unified template-loading logic to reduce I/O overhead.
  - Implemented conversion functionality between `ImageData` and image files, including both on-disk and in-memory files.
