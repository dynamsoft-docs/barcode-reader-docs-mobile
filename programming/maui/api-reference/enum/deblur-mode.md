---
layout: default-layout
title: EnumDeblurMode - Dynamsoft Barcode Reader MAUI
description: Enumeration EnumDeblurMode of DBR MAUI Edition defines the modes for extracting barcode data during the final phase of the barcode decoding process
keywords: barcode format, MAUI, OneD, QR Code, GS1 Databar
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumDeblurMode
---

# EnumDeblurMode

Enumeration `EnumDeblurMode` specifies the image processing algorithms applied to the localized zones containing barcodes, aimed at generating a binary image for extracting barcode data during the final phase of the barcode decoding process.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
namespace Dynamsoft.DBR.Maui
{
    public enum EnumDeblurMode : long
    {
        /** Skips the process, no deblurring is applied. */
        DM_SKIP = 0,
        /** Applies a direct binarization algorithm for generating the binary image. */
        DM_DIRECT_BINARIZATION = 1,
        /** Utilizes a threshold binarization algorithm for generating the binary image, dynamically determining the threshold based on the image content. */
        DM_THRESHOLD_BINARIZATION = 2,
        /** Employs a gray equalization algorithm to adjust the contrast and brightness, improving the clarity of the gray-scale image before binarization. */
        DM_GRAY_EQUALIZATION = 4,
        /** Implements a smoothing algorithm to reduce noise and artifacts, smoothing out the gray-scale image before binarization. */
        DM_SMOOTHING = 8,
        /** Uses a morphing algorithm to enhance the gray-scale image before binarization. */
        DM_MORPHING = 16,
        /** Engages in a deep analysis of the grayscale image based on the barcode format to intelligently generate the optimized binary image, tailored to complex or severely blurred images. */
        DM_DEEP_ANALYSIS = 32,
        /** Applies a sharpening algorithm to enhance the edges and details of the barcode, making it more distinguishable on the gray-scale image before binarization. */
        DM_SHARPENING = 64,
        /** Decodes the barcodes based on the binary image obtained during the localization process. */
        DM_BASED_ON_LOC_BIN = 128,
        /** Combines sharpening and smoothing algorithms for a comprehensive deblurring effect, targeting both clarity and smoothness of the gray-scale image before binarization. */
        DM_SHARPENING_SMOOTHING = 256
    }
}
```
