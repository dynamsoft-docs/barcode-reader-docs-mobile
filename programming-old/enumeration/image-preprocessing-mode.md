---
layout: default-layout
title: EnumImagePreprocessingMode
description: Use this enum data type to set constants for image preprocessing mode resisting mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumImagePreprocessingMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumImagePreprocessingMode
permalink: /programming/enumeration/image-preprocessing-mode.html
ignore: true
---


# EnumImagePreprocessingMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumImagePreprocessingMode {
    public static final int IPM_GENERAL = 2;
    public static final int IPM_AUTO = 1;
    public static final int IPM_GRAY_EQUALIZE = 4;
    public static final int IPM_GRAY_SMOOTH = 8;
    public static final int IPM_SHARPEN_SMOOTH = 16;
    public static final int IPM_MORPHOLOGY = 32;
    public static final int IPM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumImagePreprocessingMode)
{
    /** Not supported yet. */
    EnumImagePreprocessingModeAuto = 0x01,
    /** Take the unpreprocessed image as the preprocessed result for further reference. */
    EnumImagePreprocessingModeGeneral = 0x02,
    /** Preprocesses the image using the gray equalization algorithm. Check @ref IPM for available argument settings.*/
    EnumImagePreprocessingModeGrayEqualize = 0x04,
    /** Preprocesses the image using the gray smoothing algorithm. Check @ref IPM for available argument settings.*/
    EnumImagePreprocessingModeGraySmooth = 0x08,
    /** Preprocesses the image using the sharpening and smoothing algorithm. Check @ref IPM for available argument settings.*/
    EnumImagePreprocessingModeSharpenSmooth = 0x10,
    /** Preprocesses the image using the morphology algorithm. Check @ref IPM for available argument settings.*/
    EnumImagePreprocessingModeMorphology = 0x20,
    /** Skips image preprocessing */
    EnumImagePreprocessingModeSkip = 0x00
};
```
>
```swift
public enum EnumImagePreprocessingMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Take the unpreprocessed image as the preprocessed result for further reference. */
    general = 0x02
    /** Preprocesses the image using the gray equalization algorithm. Check @ref IPM for available argument settings.*/
    grayEqualize = 0x04
    /** Preprocesses the image using the gray smoothing algorithm. Check @ref IPM for available argument settings.*/
    graySmooth = 0x08
    /** Preprocesses the image using the sharpening and smoothing algorithm. Check @ref IPM for available argument settings.*/
    sharpenSmooth = 0x10
    /** Preprocesses the image using the morphology algorithm. Check @ref IPM for available argument settings.*/
    morphology = 0x20
    /** Skips image preprocessing */
    skip = 0x00
}
```
