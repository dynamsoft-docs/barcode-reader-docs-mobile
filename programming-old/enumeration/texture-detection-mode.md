---
layout: default-layout
title: EnumTextureDetectionMode
description: Use this enum data type to set constants for texture detection mode of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumTextureDetectionMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumTextureDetectionMode
permalink: /programming/enumeration/texture-detection-mode.html
---


# EnumTextureDetectionMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumTextureDetectionMode {
    public static final int TDM_AUTO = 1;
    public static final int TDM_GENERAL_WIDTH_CONCENTRATION = 2;
    public static final int TDM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumTextureDetectionMode)
{
    /** Not supported yet. */
    EnumTextureDetectionModeAuto = 0X01,
    /** Detects texture using the general algorithm. Check @ref TDM for available argument settings.*/
    EnumTextureDetectionModeGeneralWidthConcentration = 0X02,
    /** Skips texture detection. */
    EnumTextureDetectionModeSkip = 0x00
};
```
>
```swift
public enum EnumTextureDetectionMode : Int{
    /** Not supported yet. */
    auto = 0X01
    /** Detects texture using the general algorithm. Check @ref TDM for available argument settings.*/
    generalWidthConcentration = 0X02
    /** Skips texture detection. */
    skip = 0x00
}
```
