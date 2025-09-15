---
layout: default-layout
title: Dynamsoft Capture Vision - Xamarin Release Notes
description: This is the release notes of Dynamsoft Capture Vision - Xamarin Edition.
keywords:  Capture Vision, Xamarin, Release Notes
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: 1.x
---

# Release Notes for Xamarin SDK - 1.x

## 1.0.5 (03/31/2023)

- Added zoom focus controlling APIs:
  - Method [`SetFocus`](../api-reference/camera-enhancer.md#setfocus) for settings the focus point and the focus mode.
  - Method [`SetZoomFactor`](../api-reference/camera-enhancer.md#setzoomfactor) for settings the zoom factor.
  - Method [`EnableFeatures`](../api-reference/camera-enhancer.md#enablefeatures) for enabling the advanced features.
  - Method [`DisableFeatures`](../api-reference/camera-enhancer.md#disablefeatures) for disabling the advanced features.
  - Method [`IsFeatureEnabled`](../api-reference/camera-enhancer.md#isfeatureenabled) for checking the state of the advanced features.
  - Property [`MaxZoomFactor`](../api-reference/camera-enhancer.md#maxzoomfactor) for obtaining the maximum zoom ability of the device.
  - Property [`AutoZoomRange`](../api-reference/camera-enhancer.md#autozoomrange) for restricting the range of the auto-zoom feature.
  - Enumeration [`EnumEnhancerFeatures`](../api-reference/enum-enhancer-features.md) for specifying the advanced features, which include auto zoom, enhanced focus, et al.
  - Enumeration [`EnumFocusMode`](../api-reference/enum-focus-mode.md) for settings the focus mode.
  - Class [`Range`](../api-reference/class-range.md) for specifying the auto zoom range.

## 1.0.4 (03/14/2023)

- Added property `BarcodeBytes` to class [`BarcodeResult`](../api-reference/class-barcode-result.md)

## 1.0.3 (02/14/2023)

- Fixed a crash bug on the devices that do not support 16:9 size resolution.

## 1.0.2 (12/20/2022)

- Added [`ScanRegionVisile`](../api-reference/camera-enhancer.md#scanregionvisible) in interface `IDCVCameraEnhancer` so that users can hide the **scan region** on the UI.
- Added a new method [`EnableResultVerification`](../api-reference/barcode-reader.md#enableresultverification) in interface `IDCVBarcodeReader` to improve the accuracy of barcode results for video streaming barcode decoding.
- Added new methods [`EnableDuplicateFilter`](../api-reference/barcode-reader.md#enableduplicatefilter) and [`DuplicateForgetTime`](../api-reference/barcode-reader.md#duplicateforgettime) in interface `IDCVBarcodeReader` to filter out the duplicate results in a period of time for video barcode decoding.
- Added [`MinImageReadingInterval`](../api-reference/barcode-reader.md#minimagereadinginterval) to set the minimum interval between two barcode decoding.
- Added two new parameters `MinResultConfidence` and `MinBarcodeTextLength` in class [`DBRRuntimeSettings`](../api-reference/class-dbr-runtime-settings.md) to filter out unqualified barcode results.

## 1.0.1 (10/17/2022)

- Fixed a duplicate symbol issue.

## 1.0.0 (08/04/2022)

### HighLights

- The first release of DBR Xamarin.Forms SDK.
