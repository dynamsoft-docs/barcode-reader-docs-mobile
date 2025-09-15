---
layout: default-layout
title: EnumDPMCodeReadingMode
description: Use this enum data type to set constants for DPM code reading mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumDPMCodeReadingMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumDPMCodeReadingMode
permalink: /programming/enumeration/dpm-code-reading-mode.html
ignore: true
---


# EnumDPMCodeReadingMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumDPMCodeReadingMode {
    public static final int DPMCRM_AUTO = 1;
    public static final int DPMCRM_GENERAL = 2;
    public static final int DPMCRM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumDPMCodeReadingMode)
{
    /** Not supported yet. */
    EnumDPMCodeReadingModeAuto = 0x01,
    /** Reads DPM code using the general algorithm.
     When this mode is set, the library will automatically add EnumLocalizationModeStatisticsMarks to EnumLocalizationMode and add a EnumBinarizationModeLocalBlock to EnumBinarizationMode which is with arguments: BlockSizeX=0, BlockSizeY=0, EnableFillBinaryVacancy=0, ImagePreprocessingModesIndex=1, ThreshValueCoefficient=15 if you dosen't set them.*/
    EnumDPMCodeReadingModeGeneral = 0x02,
    /** Skips the DPM code reading. */
    EnumDPMCodeReadingModeSkip = 0x00
};
```
>
```swift
public enum EnumDPMCodeReadingMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Reads DPM code using the general algorithm.
     When this mode is set, the library will automatically add EnumLocalizationMode.statisticsMarks to EnumLocalizationMode and add a EnumBinarizationMode.localBlock to EnumBinarizationMode which is with arguments: BlockSizeX=0, BlockSizeY=0, EnableFillBinaryVacancy=0, ImagePreprocessingModesIndex=1, ThreshValueCoefficient=15 if you dosen't set them.*/
    general = 0x02
    /** Skips the DPM code reading. */
    skip = 0x00
}
```
