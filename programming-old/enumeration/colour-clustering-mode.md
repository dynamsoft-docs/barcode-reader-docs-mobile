---
layout: default-layout
title: EnumColourClusteringMode
description: Use this enum data type to set constants for colour clustering mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumColourClusteringMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumColourClusteringMode
permalink: /programming/enumeration/colour-clustering-mode.html
ignore: true
---


# EnumColourClusteringMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumColourClusteringMode {
    public static final int CCM_AUTO = 1;
    public static final int CCM_GENERAL_HSV = 2;
    public static final int CCM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumColourClusteringMode)
{
    /** Not supported yet. */
    EnumColourClusteringModeAuto = 0x01,
    /** Clusters colours using the general algorithm based on HSV. Check @ref CCM for available argument settings.*/
    EnumColourClusteringModeGeneralHSV = 0x02,
    /** Skips colour clustering. */
    EnumColourClusteringModeSkip = 0x00
};
```
>
```swift
public enum EnumColourClusteringMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Clusters colours using the general algorithm based on HSV. Check @ref CCM for available argument settings.*/
    generalHSV = 0x02
    /** Skips colour clustering. */
    skip = 0x00
}
```
