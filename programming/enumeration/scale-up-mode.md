---
layout: default-layout
title: EnumScaleUpMode
description: Use this enum data type to set constants for scale up mode of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumScaleUpMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumScaleUpMode
permalink: /programming/enumeration/scale-up-mode.html
ignore: true
---


# EnumScaleUpMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumScaleUpMode {
    public static final int SUM_AUTO = 1;
    public static final int SUM_LINEAR_INTERPOLATION = 2;
    public static final int SUM_NEAREST_NEIGHBOUR_INTERPOLATION = 4;
    public static final int SUM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumScaleUpMode)
{
    /** The library choose an interpolation method automatically to scale up. */
    EnumScaleUpModeAuto = 0x01,
    /** Scales up using the linear interpolation method. Check @ref SUM for available argument settings. */
    EnumScaleUpModeLinearInterpolation = 0x02,
    /** Scales up the barcode using the nearest-neighbour interpolation method. Check @ref SUM for available argument settings. */
    EnumScaleUpModeNearestNeighbourInterpolation = 0x04,
    /** Skip the scale-up process.*/
    EnumScaleUpModeSkip = 0x00
};
```
>
```swift
public enum EnumScaleUpMode : Int{
    /** The library choose an interpolation method automatically to scale up. */
    auto = 0x01
    /** Scales up using the linear interpolation method. Check @ref SUM for available argument settings. */
    linearInterpolation = 0x02
    /** Scales up the barcode using the nearest-neighbour interpolation method. Check @ref SUM for available argument settings. */
    nearestNeighbourInterpolation = 0x04
    /** Skip the scale-up process.*/
    skip = 0x00
}
```
