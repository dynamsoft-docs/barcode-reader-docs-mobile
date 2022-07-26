---
layout: default-layout
title: EnumBarcodeColourMode 
description: Use this enum data type to set constants for colour mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumBarcodeColourMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumBarcodeColourMode
permalink: /programming/enumeration/barcode-colour-mode.html
---


# EnumBarcodeColourMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumBarcodeColourMode {
    public static final int BICM_DARK_ON_LIGHT = 1;
    public static final int BICM_LIGHT_ON_DARK = 2;
    public static final int BICM_DARK_ON_DARK = 4;
    public static final int BICM_LIGHT_ON_LIGHT = 8;
    public static final int BICM_DARK_LIGHT_MIXED = 16;
    public static final int BICM_DARK_ON_LIGHT_DARK_SURROUNDING = 32;
    public static final int BICM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumBarcodeColourMode)
{
   /** Dark items on the light background. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeDarkOnLight = 0x01,
   /** Light items on the dark background. Not supported yet. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeLightOnDark = 0x02,
   /** Dark items on the dark background. Not supported yet. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeDarkOnDark = 0x04,
   /** Light items on the light background. Not supported yet. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeLightOnLight = 0x08,
   /** The background is mixed by dark and light. Not supported yet. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeDarkLightMixed = 0x10,
   /** Dark on light items on the dark background. Check @ref BICM for available argument settings.*/
   EnumBarcodeColourModeDarkOnLightDarkSurrounding = 0x20,
   /** Skips the barcode colour operation.  */
   EnumBarcodeColourModeSkip = 0x00
};
```
>
```swift
public enum EnumBarcodeColourMode : Int{
    darkOnLight = 0x01
    lightOnDark = 0x02
    darkOnDark = 0x04
    lightOnLight = 0x08
    darkLightMixed = 0x10
    darkOnLightDarkSurrounding = 0x20
    skip = 0x00
}
```
