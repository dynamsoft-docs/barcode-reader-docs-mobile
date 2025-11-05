---
layout: default-layout
title: EnumGrayscaleEnhancementMode - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumGrayscaleEnhancementMode of DBR Flutter Edition defines the modes for extracting barcode data during the final phase of the barcode decoding process
keywords: barcode format, Flutter, OneD, QR Code, GS1 Databar, barcode reader, settings, grayscale
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumGrayscaleEnhancementMode
---

# EnumGrayscaleEnhancementMode

`EnumGrayscaleEnhancementMode` is an enumeration that determines which grayscale enhancement modes the library will apply before the detection process to improve the read rate of the barcodes in a given image or frame.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumGrayscaleEnhancementMode {
    skip,
    auto,
    general,
    grayEqualize,
    graySmooth,
    sharpenSmooth,
    end
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `skip` | Disables any grayscale image preprocessing. Selecting this mode skips the preprocessing step, passing the image through to subsequent operations without modification. |
| `auto` | Automatic selection of grayscale enhancement mode which is currently not supported. Future implementations may automatically choose the most suitable enhancement based on image analysis. |
| `general` | Uses the original, unprocessed image for subsequent operations. This mode is selected when no specific grayscale enhancement is required, maintaining the image in its natural state. |
| `grayEqualize` | Applies a grayscale equalization algorithm to the image, enhancing contrast and detail in gray level. Suitable for images with poor contrast. |
| `graySmooth` | Implements a grayscale smoothing algorithm to reduce noise and smooth the image. This can be beneficial for images with high levels of grain or noise. |
| `sharpenSmooth` | Enhances the image by applying both sharpening and smoothing algorithms. This mode aims to increase clarity and detail while reducing noise, offering a balanced approach to image preprocessing. |
| `end` | Placeholder value with no functional meaning. |
