---
layout: default-layout
title: MAUI Release Notes v10.x - Dynamsoft Barcode Reader
description: This is the release notes page of Dynamsoft Barcode Reader for MAUI SDK v10.x.
keywords: release notes, android, version 10.x,
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for MAUI SDK - 10.x

## 10.4.2002 (11/04/2024)

### Fixed

- Fixed a bug that could cause the build to fail when AOT compilation is enabled.

## 10.4.2000 (10/24/2024)

### New

- Override the method Capture to support more image formats:
  - Capture(byte[] fileBytes)
  - Capture(ImageData imageData)
- Added a new method [`InitSettingsFromFileAsync`]({{ site.dcv_maui_api }}capture-vision-router/settings.html#initsettingsfromfileasync) for initializing settings from a file.
- Added a new class [`CoreModule`]({{ site.dcv_maui_api }}core/core-module.html) to get the version of Dynamsoft.Core.Maui
- Added a new class [`ImageProcessingModule`]({{ site.dcv_maui_api }}dip/image-processing-module.html) to get the version of Dynamsoft.ImageProcessing.Maui
- Added a new class [`LicenseModule`]({{ site.dcv_maui_api }}license/license-module.html) to get the version of Dynamsoft.License.Maui
- Added to-the-latest overlapping feature. You can use [`enableLatestOverlapping`]({{ site.dcv_maui_api }}utility/multi-frame-result-cross-filter.html#enablelatestoverlapping) method of [`MultiFrameResultCrossFilter`]({{ site.dcv_maui_api }}utility/multi-frame-result-cross-filter.html) class to enable this feature.
- Support more camera selections. Via the [`SelectCamera`]({{ site.dce_maui_api }}camera-enhancer.html#selectcamera) methods, you can specify the following camera positions:
  - `CP_BACK_ULTRA_WIDE`
  - `CP_BACK_DUAL_WIDE_AUTO`
- Added the following APIs to support adding interactable UI elements:
  - Class [`ImageEditorView`]({{ site.dce_maui_api }}image-editor-view.html)
  - Class [`DrawingLayer`]({{ site.dce_maui_api }}drawing-layer.html)
  - Class [`DrawingItem`]({{ site.dce_maui_api }}drawing-item.html)
  - Class [`QuadDrawingItem`]({{ site.dce_maui_api }}quad-drawing-item.html)
  - Enumeration [`EnumDrawingLayerId`]({{ site.dce_maui_api }}enum/drawing-layer-id.html)
  - Enumeration [`EnumDrawingStyleId`]({{ site.dce_maui_api }}enum/drawing-style-id.html)
- Added new methods [`TurnOnTorch`]({{ site.dce_maui_api }}camera-enhancer.html#turnontorch) & [`TurnOffTorch`]({{ site.dce_maui_api }}camera-enhancer.html#turnofftorch) to the class [`CameraEnhancer`]({{ site.dce_maui_api }}camera-enhancer.html).
- Added a new class [`CameraEnhancerModule`]({{ site.dce_maui_api }}camera-enhancer-module.html) to get the version of Dynamsoft.CameraEnhancer.Maui
- Added new APIs to the class [`CameraView`]({{ site.dce_maui_api }}camera-view.html) to use the new UI APIs.

## 10.2.1101 (06/20/2024)

{%- include release-notes/product-highlight-10.0.0.md -%}
