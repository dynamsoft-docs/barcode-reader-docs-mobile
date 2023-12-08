---
layout: default-layout
title: EnumLocalizationMode
description: This page shows the localization modes of Dynamsoft Barcode Reader mobile SDK.
keywords: EnumLocalizationMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumLocalizationMode
permalink: /programming/enumeration/localization-mode.html
---


# EnumLocalizationMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumLocalizationMode {
    public static final int LM_AUTO = 1;
    public static final int LM_CONNECTED_BLOCKS = 2;
    public static final int LM_STATISTICS = 4;
    public static final int LM_LINES = 8;
    public static final int LM_SCAN_DIRECTLY = 16;
    public static final int LM_STATISTICS_MARKS = 32;
    public static final int LM_STATISTICS_POSTAL_CODE = 64;
    public static final int LM_CENTRE = 128;
    public static final int LM_ONED_FAST_SCAN = 256;
    public static final int LM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumLocalizationMode)
{
    /** Not supported yet. */
    EnumLocalizationModeAuto = 0x01,
    /** Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
    EnumLocalizationModeConnectedBlocks = 0x02,
    /** Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
    EnumLocalizationModeStatistics = 0x04,
    /** Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes.  */
    EnumLocalizationModeLines = 0x08,
    /** Localizes barcodes quickly. This mode is recommended for interactive scenarios. Check @ref LM for available argument settings.*/
    EnumLocalizationModeScanDirectly = 0x10,
    /** Localizes barcodes by groups of marks.This is optimized for DPM codes. */
    EnumLocalizationModeStatisticsMarks = 0x20,
    /** Localizes barcodes by groups of connected blocks and lines. This is optimized for postal codes.*/
    EnumLocalizationModeStatisticsPostalCode = 0x40,
    /** Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
    EnumLocalizationModeCentre = 0x80,
    /** Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
    EnumLocalizationModeOneDFastScan = 0x100,
    /** Skips the localization. */
    EnumLocalizationModeSkip = 0x00
};
```
>
```swift
public enum EnumLocalizationMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
    connectedBlocks = 0x02
    /** Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
    statistics = 0x04
    /** Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes.  */
    lines = 0x08
    /** Localizes barcodes quickly. This mode is recommended for interactive scenarios. Check @ref LM for available argument settings.*/
    scanDirectly = 0x10
    /** Localizes barcodes by groups of marks.This is optimized for DPM codes. */
    statisticsMarks = 0x20
    /** Localizes barcodes by groups of connected blocks and lines. This is optimized for postal codes.*/
    statisticsPostalCode = 0x40
    /** Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
    centre = 0x80
    /** Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
    oneDFastScan = 0x100
    /** Skips the localization. */
    skip = 0x00
}
```
