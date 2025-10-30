---
layout: default-layout
title: EnumDeblurMode - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumDeblurMode of DBR Flutter Edition defines the modes for extracting barcode data during the final phase of the barcode decoding process
keywords: barcode format, Flutter, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumDeblurMode
---

# EnumDeblurMode

`EnumDeblurMode` is an enumeration that specifies the image processing algorithms applied to the localized zones containing barcodes, with the main aim being to generate a binary image for extracting barcode data during the final phase of the barcode decoding process.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumDeblurMode {
    skip,
    directBinarization,
    thresholdBinarization,
    grayEqualization,
    smoothing,
    morphing,
    deepAnalysis,
    sharpening,
    basedOnLocBin,
    sharpeningSmoothing,
    neuralNetwork,
    end
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `skip` | Skips the process, no deblurring is applied. |
| `directBinarization` | Applies a direct binarization algorithm for generating the binary image. |
| `thresholdBinarization` | Utilizes a threshold binarization algorithm for generating the binary image, dynamically determining the threshold based on the image content. |
| `grayEqualization` | Employs a gray equalization algorithm to adjust the contrast and brightness, improving the clarity of the gray-scale image before binarization. |
| `smoothing` | Implements a smoothing algorithm to reduce noise and artifacts, smoothing out the gray-scale image before binarization. |
| `morphing` | Uses a morphing algorithm to enhance the gray-scale image before binarization. |
| `deepAnalysis` | Engages in a deep analysis of the grayscale image based on the barcode format to intelligently generate the optimized binary image, tailored to complex or severely blurred images. |
| `sharpening` | Applies a sharpening algorithm to enhance the edges and details of the barcode, making it more distinguishable on the gray-scale image before binarization. |
| `basedOnLocBin` | Decodes the barcodes based on the binary image obtained during the localization process. |
| `sharpeningSmoothing` | Combines sharpening and smoothing algorithms for a comprehensive deblurring effect, targeting both clarity and smoothness of the gray-scale image before binarization. |
| `neuralNetwork` | Use the deep learning algorithm to recognize the barcodes. |
| `end` | Placeholder value with no functional meaning. |
