---
layout: default-layout
title: Dynamsoft Capture Vision - Cordova Release Notes
description: This is the release notes of Dynamsoft Capture Vision - Cordova Edition.
keywords:  Capture Vision, Cordova, Release Notes
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: 1.x
---

# Release Notes for Cordova SDK - 1.x

## 1.0.7 (12/29/2025)

### New

- Supported 16 KB page sizes

## 1.0.5 (12/20/2023)

### New

- Added methods `setMinImageReadingInterval` & `getMinImageReadingInterval` to control the image reading interval.

### Fixed

- Fixed a bug where UI elements are not removed when the `CameraView` disappears.
- Fixed a crash bug by internal updates.

## 1.0.4 (02/14/2023)

### Fixed

- Fixed a bug that scan region might not be displayed on the view when reopening the camera.

## 1.0.3 (01/12/2023)

### Improved

- Optimized the internal code to support more usage scenarios.

### Fixed

- Fixed a bug that the camera view is not correctly displayed when switching from one scan page to another.
- Fixed a bug that the scan region is not removed from `DCECameraView` when it is canceled.

## 1.0.2 (11/24/2022)

- Fixed a bug that camera view is not displayed correctly when the camera is re-opened.
- Fixed a bug that the UI elements on the camera view are not removed when the camera is closed.

## 1.0.1 (09/22/2022)

- Fixed a bug that a previously captured video frame is not removed when the camera is closed.

## 1.0.0 (08/23/2022)

- The first release of DBR Cordova SDK.
