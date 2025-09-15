---
layout: default-layout
title: EnumColourConversionMode
description: Use this enum data type to set constants for colour conversion mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumColourConversionMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumColourConversionMode
permalink: /programming/enumeration/colour-conversion-mode.html
ignore: true
---


# EnumColourConversionMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumColourConversionMode {
    public static final int CICM_GENERAL = 1;
    public static final int CICM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumColourConversionMode)
{
    /** Converts a colour image to a grayscale image using the general algorithm. Check @ref CICM for available argument settings.*/
    EnumColourConversionModeGeneral = 0x01,
    /** Skips colour conversion. */
    EnumColourConversionModeSkip = 0x00
};
```
>
```swift
public enum EnumColourConversionMode : Int{
    /** Converts a colour image to a grayscale image using the general algorithm. Check @ref CICM for available argument settings.*/
    general = 0x01
    /** Skips colour conversion. */
    skip = 0x00
}
```
