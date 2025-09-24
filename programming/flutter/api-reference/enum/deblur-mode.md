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
enum EnumDeblurMode
{
    /** Skips the process, no deblurring is applied. */
    skip,
    /** Applies a direct binarization algorithm for generating the binary image. */
    directBinarization,
    /** Utilizes a threshold binarization algorithm for generating the binary image, dynamically determining the threshold based on the image content. */
    thresholdBinarization,
    /** Employs a gray equalization algorithm to adjust the contrast and brightness, improving the clarity of the gray-scale image before binarization. */
    grayEqualization,
    /** Implements a smoothing algorithm to reduce noise and artifacts, smoothing out the gray-scale image before binarization. */
    smoothing,
    /** Uses a morphing algorithm to enhance the gray-scale image before binarization. */
    morphing,
    /** Engages in a deep analysis of the grayscale image based on the barcode format to intelligently generate the optimized binary image, tailored to complex or severely blurred images. */
    deepAnalysis,
    /** Applies a sharpening algorithm to enhance the edges and details of the barcode, making it more distinguishable on the gray-scale image before binarization. */
    sharpening,
    /** Decodes the barcodes based on the binary image obtained during the localization process. */
    basedOnLocBin,
    /** Combines sharpening and smoothing algorithms for a comprehensive deblurring effect, targeting both clarity and smoothness of the gray-scale image before binarization. */
    sharpeningSmoothing,
    /** Use the deep learning algorithm to recognize the barcodes. */
    neuralNetwork,
    /**Placeholder value with no functional meaning. */
    end
}
```
