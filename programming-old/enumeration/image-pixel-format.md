---
layout: default-layout
title: EnumImagePixelFormat
description: Use this enum data type to set constants for image pixel format of barcodes in Dynamsoft Barcode Reader for JavaScript.
keywords: EnumImagePixelFormat, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumImagePixelFormat
permalink: /programming/enumeration/image-pixel-format.html
---


# EnumImagePixelFormat

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumImagePixelFormat {
    public static final int IPF_BINARY = 0;
    public static final int IPF_BINARYINVERTED = 1;
    public static final int IPF_GRAYSCALED = 2;
    public static final int IPF_NV21 = 3;
    public static final int IPF_RGB_565 = 4;
    public static final int IPF_RGB_555 = 5;
    public static final int IPF_RGB_888 = 6;
    public static final int IPF_ARGB_8888 = 7;
    public static final int IPF_RGB_161616 = 8;
    public static final int IPF_ARGB_16161616 = 9;
    public static final int IPF_ABGR_8888 = 10;
    public static final int IPF_ABGR_16161616 = 11;
    public static final int IPF_BGR_888 = 12;
}
```
>
```objc
typedef NS_ENUM(NSInteger, EnumImagePixelFormat)
{
    /** 0:black, 1:white */
    EnumImagePixelFormatBinary = 0,
    /** 0:white, 1:black */
    EnumImagePixelFormatBinaryInverted = 1,
    /** 8-bit gray */
    EnumImagePixelFormatGrayScaled = 2,
    /** NV21 */
    EnumImagePixelFormatNV21 = 3,
    /** 16bit with RGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatRGB_565 = 4,
    /** 16bit with RGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatRGB_555 = 5,
    /** 24bit with RGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatRGB_888 = 6,
    /** 32bit with ARGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatARGB_8888 = 7,
    /** 48bit with RGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatRGB_161616 = 8,
    /** 64bit with ARGB channel order stored in memory from high to low address*/
    EnumImagePixelFormatARGB_16161616 = 9,
    /** 32bit with ABGB channel order stored in memory from high to low address */
    EnumImagePixelFormatABGR_8888 = 10,
    /** 64bit with ABGR channel order stored in memory from high to low address*/
    EnumImagePixelFormatABGR_16161616 = 11,
    /** 24bit with BGR channel order stored in memory from high to low address*/
    EnumImagePixelFormatBGR_888 = 12
};
```
>
```swift
public enum EnumImagePixelFormat : Int{
    /** 0:black, 1:white */
    binary = 0
    /** 0:white, 1:black */
    binaryInverted = 1
    /** 8-bit gray */
    grayScaled = 2
    /** NV21 */
    NV21 = 3
    /** 16bit with RGB channel order stored in memory from high to low address*/
    RGB_565 = 4
    /** 16bit with RGB channel order stored in memory from high to low address*/
    RGB_555 = 5
    /** 24bit with RGB channel order stored in memory from high to low address*/
    RGB_888 = 6
    /** 32bit with ARGB channel order stored in memory from high to low address*/
    ARGB_8888 = 7
    /** 48bit with RGB channel order stored in memory from high to low address*/
    RGB_161616 = 8
    /** 64bit with ARGB channel order stored in memory from high to low address*/
    ARGB_16161616 = 9
    /** 32bit with ABGB channel order stored in memory from high to low address */
    ABGR_8888 = 10
    /** 64bit with ABGR channel order stored in memory from high to low address*/
    ABGR_16161616 = 11
    /** 24bit with BGR channel order stored in memory from high to low address*/
    BGR_888 = 12
}
```
