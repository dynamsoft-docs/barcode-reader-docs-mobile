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

## 11.0.5000 (07/25/2025)

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
