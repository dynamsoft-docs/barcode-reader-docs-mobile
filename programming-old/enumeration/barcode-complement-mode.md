---
layout: default-layout
title: EnumBarcodeComplementMode
description: Use this enum data type to set constants for complement mode of barcodes in your Dynamsoft Barcode Reader project.
keywords: EnumBarcodeComplementMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumBarcodeComplementMode(Mobile)
permalink: /programming/enumeration/barcode-complement-mode.html
ignore: true
---


# EnumBarcodeComplementMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumBarcodeComplementMode {
    public static final int BCM_AUTO = 1;
    public static final int BCM_GENERAL = 2;
    public static final int BCM_SKIP = 0;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumBarcodeComplementMode)
{
   /** Not supported yet.*/
   EnumBarcodeComplementModeAuto = 0x01,
   /** Complements the barcode using the general algorithm.*/
   EnumBarcodeComplementModeGeneral = 0x02,
   /**Skips the barcode complement. */
   EnumBarcodeComplementModeSkip = 0x00
};
```
>
```swift
public enum EnumBarcodeComplementMode : Int{
    auto = 0x01
    general = 0x02
    skip = 0x00
}
```
