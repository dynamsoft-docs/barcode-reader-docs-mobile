---
layout: default-layout
title: EnumBinarizationMode
description: Use this enum data type to set constants for binarization mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumBinarizationMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumBinarizationMode
permalink: /programming/enumeration/binarization-mode.html
---


# EnumBinarizationMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumBinarizationMode {
    public static final int BM_AUTO = 1;
    public static final int BM_LOCAL_BLOCK = 2;
    public static final int BM_THRESHOLD = 4;
    public static final int BM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumBinarizationMode)
{
    /** Not supported yet. */
    EnumBinarizationModeAuto = 0x01,
    /** Binarizes the image based on the local block. Check @ref BM for available argument settings.*/
    EnumBinarizationModeLocalBlock = 0x02,
    /** Performs image binarization based on the given threshold. Check @ref BM for available argument settings.*/
    EnumBinarizationModeThreshold = 0x04,
    /** Skips binarization.*/
    EnumBinarizationModeSkip = 0x00
};
```
>
```swift
public enum EnumBinarizationMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Binarizes the image based on the local block. Check @ref BM for available argument settings.*/
    localBlock = 0x02
    /** Performs image binarization based on the given threshold. Check @ref BM for available argument settings.*/
    threshold = 0x04
    /** Skips binarization.*/
    skip = 0x00
}
```
