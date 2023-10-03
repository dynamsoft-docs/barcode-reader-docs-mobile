---
layout: default-layout
title: EnumRegionPredetectionMode
description: Use this enum data type to set constants for region predetection mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumRegionPredetectionMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumRegionPredetectionMode
permalink: /programming/enumeration/region-predetection-mode.html
---


# EnumRegionPredetectionMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumRegionPredetectionMode {
    public static final int RPM_AUTO = 1;
    public static final int RPM_GENERAL = 2;
    public static final int RPM_GENERAL_RGB_CONTRAST = 4;
    public static final int RPM_GENERAL_GRAY_CONTRAST = 8;
    public static final int RPM_GENERAL_HSV_CONTRAST = 16;
    public static final int RPM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumRegionPredetectionMode)
{
    /** The library will automatically choose the algorithm to detect region. */
    EnumRegionPredetectionModeAuto = 0x01,
    /** Takes the whole image as a region. */
    EnumRegionPredetectionModeGeneral = 0x02,
    /** Detects region using the general algorithm based on RGB colour contrast. Check @ref RPM for available argument settings.*/
    EnumRegionPredetectionModeGeneralRGBContrast = 0x04,
    /** Detects region using the general algorithm based on gray contrast. Check @ref RPM for available argument settings.*/
    EnumRegionPredetectionModeGeneralGrayContrast = 0x08,
    /** Detects region using the general algorithm based on HSV colour contrast. Check @ref RPM for available argument settings.*/
    EnumRegionPredetectionModeGeneralHSVContrast = 0x10,
    /** Skips region detection. */
    EnumRegionPredetectionModeSkip = 0x00
};
```
>
```swift
public enum EnumRegionPredetectionMode : Int{
    /** The library will automatically choose the algorithm to detect region. */
    auto = 0x01
    /** Takes the whole image as a region. */
    general = 0x02
    /** Detects region using the general algorithm based on RGB colour contrast. Check @ref RPM for available argument settings.*/
    generalRGBContrast = 0x04
    /** Detects region using the general algorithm based on gray contrast. Check @ref RPM for available argument settings.*/
    generalGrayContrast = 0x08
    /** Detects region using the general algorithm based on HSV colour contrast. Check @ref RPM for available argument settings.*/
    generalHSVContrast = 0x10
    /** Skips region detection. */
    skip = 0x00
}
```
