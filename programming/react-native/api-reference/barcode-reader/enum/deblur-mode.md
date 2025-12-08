---
layout: default-layout
title: EnumDeblurMode - Dynamsoft Barcode Reader React Native
description: Enumeration EnumDeblurMode of DBR React Native Edition defines the modes for extracting barcode data during the final phase of the barcode decoding process
keywords: barcode format, React Native, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumDeblurMode
---

# EnumDeblurMode

`EnumDeblurMode` is an enumeration that specifies the image processing algorithms applied to the localized zones containing barcodes, with the main aim being to generate a binary image for extracting barcode data during the final phase of the barcode decoding process.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
enum EnumDeblurMode {
  DM_END = -1,
  DM_SKIP = 0x0,
  DM_DIRECT_BINARIZATION = 0x1,
  DM_THRESHOLD_BINARIZATION = 0x2,
  DM_GRAY_EQUALIZATION = 0x4,
  DM_SMOOTHING = 0x8,
  DM_MORPHING = 0x10,
  DM_DEEP_ANALYSIS = 0x20,
  DM_SHARPENING = 0x40,
  DM_BASED_ON_LOC_BIN = 0x80,
  DM_SHARPENING_SMOOTHING = 0x100,
  DM_NEURAL_NETWORK = 0x200
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `DM_SKIP` | Skips the process, no deblurring is applied. |
| `DM_DIRECT_BINARIZATION` | Applies a direct binarization algorithm for generating the binary image. |
| `DM_THRESHOLD_BINARIZATION` | Utilizes a threshold binarization algorithm for generating the binary image, dynamically determining the threshold based on the image content. |
| `DM_GRAY_EQUALIZATION` | Employs a gray equalization algorithm to adjust the contrast and brightness, improving the clarity of the gray-scale image before binarization. |
| `DM_SMOOTHING` | Implements a smoothing algorithm to reduce noise and artifacts, smoothing out the gray-scale image before binarization. |
| `DM_MORPHING` | Uses a morphing algorithm to enhance the gray-scale image before binarization. |
| `DM_DEEP_ANALYSIS` | Engages in a deep analysis of the grayscale image based on the barcode format to intelligently generate the optimized binary image, tailored to complex or severely blurred images. |
| `DM_SHARPENING` | Applies a sharpening algorithm to enhance the edges and details of the barcode, making it more distinguishable on the grayscale image before binarization. |
| `DM_BASED_ON_LOC_BIN` | Decodes the barcodes based on the binary image obtained during the localization process. |
| `DM_SHARPENING_SMOOTHING` | Combines sharpening and smoothing algorithms for a comprehensive deblurring effect, targeting both clarity and smoothness of the gray-scale image before binarization. |
| `DM_NEURAL_NETWORK` | Use the deep learning algorithm to recognize the barcodes. |
| `DM_END` | Placeholder value with no functional meaning. |

> [!NOTE]
> View more about [DeblurModes Parameters]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html#candidate-modes-introduction) page.
