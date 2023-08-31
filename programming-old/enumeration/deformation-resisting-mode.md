---
layout: default-layout
title: EnumDeformationResistingMode
description: Use this enum data type to set constants for deformation resisting mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumDeformationResistingMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumDeformationResistingMode
permalink: /programming/enumeration/deformation-resisting-mode.html
---


# EnumDeformationResistingMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumDeformationResistingMode {
    public static final int DRM_AUTO = 1;
    public static final int DRM_GENERAL = 2;
    public static final int DRM_BROAD_WARP = 4;
    public static final int DRM_LOCAL_REFERENCE = 8;
    public static final int DRM_DEWRINKLE = 16;
    public static final int DRM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumDeformationResistingMode)
{
    /** Not supported yet. */
    EnumDeformationResistingModeAuto = 0x01,
    /** Resists deformation using the general algorithm. Check @ref DRM for available argument settings.*/
    EnumDeformationResistingModeGeneral = 0x02,
    EnumDeformationResistingModeBroadWrap = 0x04,
    EnumDeformationResistingModeLocalReference = 0x08,
    EnumDeformationResistingModeDewrinkle = 0x10,
    /** Skips the deformation resisting operation. */
    EnumDeformationResistingModeSkip = 0x00
};
```
>
```swift
public enum EnumDeformationResistingMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Resists deformation using the general algorithm. Check @ref DRM for available argument settings.*/
    general = 0x02
    broadWrap = 0x04
    localReference = 0x08
    dewrinkle = 0x10
    /** Skips the deformation resisting operation. */
    skip = 0x00
}
```
