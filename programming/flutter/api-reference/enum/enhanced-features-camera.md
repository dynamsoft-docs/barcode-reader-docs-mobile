---
layout: default-layout
title: EnumEnhancedFeatures - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumEnhancedFeatures of DBR Flutter Edition defines the enhanced features of the Camera Enhancer that can be activated.
keywords: enhanced features, Flutter, camera enhancer, zoom, torch
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumEnhancedFeatures
---

# EnumEnhancedFeatures

`EnumEnhancedFeatures` is an enumeration that defines the set of enhanced features that the Camera Enhancer offers. These enhanced features can help improve the performance of the Barcode Reader or adapt it to certain difficult scenarios e.g. using auto-zoom for barcodes that are farther than normal.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumEnhancedFeatures {
    frameFilter,
    sensorControl,
    enhancedFocus,
    autoZoom,
    smartTorch,
    all
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `frameFilter` | Enables frame filtering to improve image quality, potentially leading to better read rate results. |
| `sensorControl` | Allows sensor control to automatically filter out any frames while the device is shaking. |
| `enhancedFocus` | Enhances the camera's focus capabilities, facilitating the camera to trigger auto-focus. This is especially useful for low-end mobile devices that do not have the ability to auto-focus. |
| `autoZoom` | Causes the camera to zoom in automatically when the barcode that it is trying to capture is far away, making the localization and decoding process easier for the Barcode Reader. |
| `smartTorch` | Activates the smart torch feature, which displays a torch button in the camera view when the environment brightness is low and hides the button if the brightness is high. |
| `all` | Enables all of the above enhanced features. |
