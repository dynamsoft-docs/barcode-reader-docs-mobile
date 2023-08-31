---
layout: default-layout
title: EnumPDFReadingMode
description: Use this enum data type to set constants for PDF reading mode of barcodes in Dynamsoft Barcode Reader for JavaScript..
keywords: EnumPDFReadingMode, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumPDFReadingMode
permalink: /programming/enumeration/pdf-reading-mode.html
---


# EnumPDFReadingMode

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumPDFReadingMode {
    public static final int PDFRM_AUTO = 1;
    public static final int PDFRM_VECTOR = 2;
    public static final int PDFRM_RASTER = 4;
}
```
>
```objc
typedef NS_ENUM(NSInteger,EnumPDFReadingMode)
{
    /** Lets the library choose the reading mode automatically.*/
    EnumPDFReadingModeAuto = 0x01,
    /** Detects barcode from vector data in PDF file.*/
    EnumPDFReadingModeVector = 0x02,
    /** Converts the PDF file to image(s) first, then perform barcode recognition.*/
    EnumPDFReadingModeRaster = 0x04
};
```
>
```swift
public enum EnumPDFReadingMode : Int{
    /** Lets the library choose the reading mode automatically.*/
    auto = 0x01
    /** Detects barcode from vector data in PDF file.*/
    vector = 0x02
    /** Converts the PDF file to image(s) first, then perform barcode recognition.*/
    raster = 0x04
}
```
