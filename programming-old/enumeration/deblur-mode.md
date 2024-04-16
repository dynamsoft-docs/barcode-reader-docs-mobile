---
layout: default-layout
title: EnumDeblurMode
description: Use this enum data type to set constants for deblur mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumDeblurMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumDeblurMode
permalink: /programming/enumeration/deblur-mode.html
ignore: true
---


# EnumDeblurMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumDeblurMode {
    public static final int DM_SKIP = 0;
    public static final int DM_DIRECT_BINARIZATION = 1;
    public static final int DM_THRESHOLD_BINARIZATION = 2;
    public static final int DM_GRAYE_EQULIZATION = 4;
    public static final int DM_SMOOTHING = 8;
    public static final int DM_MORPHING = 16;
    public static final int DM_DEEP_ANALYSIS = 32;
    public static final int DM_SHARPENING = 64;
    public static final int DM_BASED_ON_LOC_BIN = 128;
    public static final int DM_SHARPENING_SMOOTHING = 256;
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumDeblurMode)
{
    /**Performs deblur process using the direct binarization algorithm.*/
    EnumDeblurModeDirectBinarization = 0x01,
    /**Performs deblur process using the threshold binarization algorithm.*/
    EnumDeblurModeThresholdBinarization = 0x02,
    /**Performs deblur process using the gray equalization algorithm.*/
    EnumDeblurModeGrayEqualization = 0x04,
    /**Performs deblur process using the smoothing algorithm.*/
    EnumDeblurModeSmoothing = 0x08,
    /**Performs deblur process using the morphing algorithm.*/
    EnumDeblurModeMorphing = 0x10,
    /**Performs deblur process using the deep analysis algorithm.*/
    EnumDeblurModeDeepAnalysis = 0x20,
    /**Performs deblur process using the sharpening algorithm.*/
    EnumDeblurModeSharpening = 0x40,
    /**Performs deblur process based on the binary image from the localization process.*/
    EnumDeblurModeBasedOnLocBin = 0x80,
    /**Performs deblur process using the sharpening and smoothing algorithm.*/
    EnumDeblurModeSharpeningSmoothing = 0x100,
    /**Skips the deblur process.*/
    EnumDeblurModeSkip = 0x00
};
```
>
```swift
public enum EnumDeblurMode : Int{
    /**Performs deblur process using the direct binarization algorithm.*/
    directBinarization = 0x01
    /**Performs deblur process using the threshold binarization algorithm.*/
    thresholdBinarization = 0x02
    /**Performs deblur process using the gray equalization algorithm.*/
    grayEqualization = 0x04
    /**Performs deblur process using the smoothing algorithm.*/
    smoothing = 0x08
    /**Performs deblur process using the morphing algorithm.*/
    morphing = 0x10
    /**Performs deblur process using the deep analysis algorithm.*/
    deepAnalysis = 0x20
    /**Performs deblur process using the sharpening algorithm.*/
    sharpening = 0x40
    /**Performs deblur process based on the binary image from the localization process.*/
    basedOnLocBin = 0x80
    /**Performs deblur process using the sharpening and smoothing algorithm.*/
    sharpeningSmoothing = 0x100
    /**Skips the deblur process.*/
    skip = 0x00
}
```
