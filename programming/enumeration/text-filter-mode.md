---
layout: default-layout
title: EnumTextFilterMode
description: Use this enum data type to set constants for text filter mode of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumTextFilterMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumTextFilterMode
permalink: /programming/enumeration/text-filter-mode.html
ignore: true
---


# EnumTextFilterMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumTextFilterMode {
    public static final int TFM_AUTO = 1;
    public static final int TFM_GENERAL_CONTOUR = 2;
    public static final int TFM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumTextFilterMode)
{
    /** Not supported yet. */
    EnumTextFilterModeAuto = 0x01,
    /** Filters text using the general algorithm based on contour. Check @ref TFM for available argument settings.*/
    EnumTextFilterModeGeneralContour = 0x02,
    /** Skips text filtering. */
    EnumTextFilterModeSkip = 0x00
};
```
>
```swift
public enum EnumTextFilterMode : Int{
    /** Not supported yet. */
    auto = 0x01
    /** Filters text using the general algorithm based on contour. Check @ref TFM for available argument settings.*/
    generalContour = 0x02
    /** Skips text filtering. */
    skip = 0x00
}
```
