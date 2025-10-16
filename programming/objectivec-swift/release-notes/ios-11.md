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

## 11.2.1000 (10/16/2025)

🎉 **Milestone Release** - This version introduces groundbreaking AI-powered enhancements that significantly improve accuracy and performance across all barcode and MRZ processing scenarios.

### ✨ Key Highlights

**AI-Powered Detection & Decoding**

- 🧠 **First-to-Market AI Localization**: Revolutionary `OneDLocalization` and `DataMatrixQRCodeLocalization` neural network models for superior detection of **blurred/low-resolution 1D codes** and **DataMatrix/QR codes with missing or damaged finder patterns**.
- ⚡ **Specialized Decoders**: Cutting-edge `EAN13Decoder` and `Code128Decoder` models deliver unprecedented accuracy for **blurred and long-distance** scenarios.
- 🔍 **Enhanced Clarity Processing**: Completely redesigned `OneDDeblur` model with superior **motion blur and focus blur** recovery algorithms.
- 🎯 **Flexible Model Configuration**: Advanced [`ModelNameArray`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#mode-arguments) parameter enables on-demand model loading and precise selection for specific barcode scenarios.

**Precision Control**

- ⚙️ **Granular Deblur Methods**: Fine-tuned [`DM_DEEP_ANALYSIS`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#dm_deep_analysis) with specialized method control - `OneDGeneral`, `TwoDGeneral`, and `EAN13Enhanced` for targeted optimization.
- 🎯 **Smart Barcode Counting**: New [`ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-format-specification/expected-barcodes-count.html) parameter enables **format-specific quantity control** and **early termination optimization** for known-quantity scenarios.
- 🔍 **Advanced Region Detection**: New [`RPM_GRAY_CONSISTENCY`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html#rpm_gray_consistency) mode enables precise region detection based on **grayscale uniformity** and **local consistency** for document and label processing.

### 💡 What This Means for You

**For Challenging Barcode Scenarios**

- **Blurred conditions**: 26.5% better read rates with 44% faster processing - ideal for handheld scanning and moving objects.
- **Extended distance capability**: Breakthrough support for reading distances beyond 75cm - revolutionizing warehouse automation and high-shelf scanning.
- **Damaged 2D codes**: Enhanced detection of DataMatrix and QR codes with missing or damaged finder patterns - perfect for manufacturing and logistics applications.

**For Enterprise Integration**

- **Retail environments**: Enhanced performance for blurred handheld scanning and long-distance shelf reading.
- **Logistics & shipping**: Improved recognition for package tracking with better blur and long-distance scanning capabilities.
- **Manufacturing QC**: Improved 2D code reading on printed/etched parts with wear damage.  

**For Developers**

- **Backward Compatible**: Seamless upgrade with existing code and easy migration path.
- **Flexible Configuration**: Extensive parameter customization for specific use cases and comprehensive model configuration options.
- **Enterprise Ready**: Battle-tested stability for production environments.

### Changed

- Added a new method, [`switchCapturingTemplate`]({{ site.dcvb_ios_api }}capture-vision-router/multiple-file-processing.html#switchcapturingtemplate), which allows switching templates dynamically during the image processing workflow.
- Added a new method, [`clearDLModelBuffers`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#cleardlmodelbuffers), to release memory by clearing buffered deep learning models.
- Added a new method, [`setGlobalIntraOpNumThreads`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#setglobalintranumthreads), to configure the global number of threads used for model execution.
- Added a new button, `cameraToggleButton`, to the `CameraView`, allowing users to switch between the front and back cameras.
The following APIs are provided for configuring the `cameraToggleButton`:
  - [`setCameraToggleButton`]({{ site.dce_ios }}auxiliary-api/dcecameraview.html#setcameratogglebutton)
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
