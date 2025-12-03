---
layout: default-layout
title: React Native Release Notes - Dynamsoft Barcode Reader React Native SDK
description: This is the release notes page of Dynamsoft Barcode Reader for React Native SDK.
keywords: release notes, React Native, barcode reader
needAutoGenerateSidebar: false
breadcrumbText: Release Notes
---

# Dynamsoft Barcode Reader React Native SDK - Release Notes

## 11.2.3000 (11/06/2025)

### Highlighted Features

- Updated the SDK to Dynamsoft Capture Vision v3.2.1100 and Dynamsoft Barcode Reader v11.2.1100
- Added new image processing utilities including `ImageDrawer`, `ImageIO`, and `ImageProcessor` for enhanced image manipulation capabilities
- Introduced barcode format-specific details classes for QR codes, Aztec codes, Data Matrix codes, OneD codes, and PDF417 codes
- Enhanced camera controls with toggleable camera switching UI components

### New Features

#### CaptureVisionRouter

- Added `switchCapturingTemplate(String templateName)` method to dynamically switch between capture templates
- Added `setGlobalIntraOpNumThreads(int intraOpNumThreads)` method to configure thread pool settings
- Added `clearDLModelBuffers()` method to clear deep learning model buffers

#### Barcode Reader

- Introduced barcode format-specific details classes:
  - `AztecDetails` - Provides detailed information for Aztec codes
  - `DataMatrixDetails` - Provides detailed information for Data Matrix codes
  - `OneDCodeDetails` - Provides detailed information for 1D barcodes
  - `QRCodeDetails` - Provides detailed information for QR codes
  - `PDF417Details` - Provides detailed information for PDF417 codes
- Added `EnumQRCodeErrorCorrectionLevel` enumeration for QR code error correction levels
- Extended `BarcodeResultItem` with format-specific detail properties:
  - `qrCodeDetails` - Details specific to QR codes
  - `aztecDetails` - Details specific to Aztec codes
  - `dataMatrixDetails` - Details specific to Data Matrix codes
  - `oneDCodeDetails` - Details specific to OneD codes
  - `pdf417Details` - Details specific to PDF417 codes

#### Camera Enhancer

- Added `cameraToggleButtonVisible` property to `CameraView` to control camera toggle button visibility
- Added `cameraToggleButton` property to `CameraView` for customizable camera switching UI

#### Image Processing Utilities

- Introduced `ImageDrawer` class with:
  - `drawOnImage()` method to draw quadrilaterals on images with customizable color and thickness
- Introduced `ImageIO` class with:
  - `saveToFile()` method to save images to file system with overwrite control
- Introduced `ImageProcessor` class with comprehensive image processing capabilities:
  - `cropImage()` - Crop images using rectangular regions
  - `cropAndDeskewImage()` - Crop and deskew images using quadrilaterals with padding and size options
  - `adjustBrightness()` - Adjust image brightness
  - `adjustContrast()` - Adjust image contrast
  - `filterImage()` - Apply image filters (high pass, sharpen, smooth)
  - `convertToGray()` - Convert images to grayscale with customizable RGB weights
  - `convertToBinaryGlobal()` - Convert to binary using global thresholding
  - `convertToBinaryLocal()` - Convert to binary using local adaptive thresholding
- Added `EnumFilterType` enumeration with filter options: `highPass`, `sharpen`, and `smooth`

#### Code Parser

- Added `rawValue` property to `ParsedField` for accessing raw field values

### API Changes

#### Breaking Changes

- Moved `getOriginalImage()` method from `CaptureVisionRouter` to `IntermediateResultManager`
  - Old: `CaptureVisionRouter.getOriginalImage()`
  - New: `CaptureVisionRouter.IntermediateResultManager.getOriginalImage()`

#### Deprecations

## 11.0.5201 (08/28/2025)
