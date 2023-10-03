---
layout: default-layout
title: EnumBarcodeFormat_2
description: Use this enum data type to set constants for barcode format in your Dynamsoft Barcode Reader project.
keywords: EnumBarcodeFormat_2, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat_2
permalink: /programming/enumeration/barcode-format2.html
---


# EnumBarcodeFormat_2

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumBarcodeFormat_2 {
    public static final int BF2_NULL = 0;
    public static final int BF2_NONSTANDARD_BARCODE = 1;
    public static final int BF2_DOTCODE = 2;
    public static final int BF2_PHARMACODE = 12;
    public static final int BF2_PHARMACODE_ONE_TRACK = 4;
    public static final int BF2_PHARMACODE_TWO_TRACK = 8;
    public static final int BF2_POSTALCODE = 32505856;
    public static final int BF2_USPSINTELLIGENTMAIL = 1048576;
    public static final int BF2_POSTNET = 2097152;
    public static final int BF2_PLANET = 4194304;
    public static final int BF2_AUSTRALIANPOST = 8388608;
    public static final int BF2_RM4SCC = 16777216;
}
```
>
```objc
typedef NS_OPTIONS(NSInteger , EnumBarcodeFormat2)
{
    /** No barcode format in BarcodeFormat group 2 */
    EnumBarcodeFormat2NULL NS_SWIFT_NAME(Null) = 0x00,
    /** Nonstandard barcode */
    EnumBarcodeFormat2NONSTANDARDBARCODE = 0x01,
    /** PHARMACODE_ONE_TRACK */
    EnumBarcodeFormat2PHARMACODE_ONE_TRACK = 0x04,
    /** PHARMACODE_ONE_TRACK */
    EnumBarcodeFormat2PHARMACODE_TWO_TRACK = 0x08,
    /** PHARMACODE */
    EnumBarcodeFormat2PHARMACODE = 0x0C,
    /** DotCode Barcode.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsMarks to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2DOTCODE = 0x00000002,
    /** Combined value of EnumBarcodeFormat2USPSINTELLIGENTMAIL, EnumBarcodeFormat2POSTNET, EnumBarcodeFormat2PLANET, EnumBarcodeFormat2AUSTRALIANPOST, EnumBarcodeFormat2RM4SCC.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2POSTALCODE = 0x01F00000,
    /** USPS Intelligent Mail.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2USPSINTELLIGENTMAIL = 0x00100000,
    /** Postnet.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2POSTNET = 0x00200000,
    /** Planet.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2PLANET = 0x00400000,
    /** Australian Post.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2AUSTRALIANPOST = 0x00800000,
    /** Royal Mail 4-State Customer Barcode.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    EnumBarcodeFormat2RM4SCC = 0x01000000
};
```
>
```swift
public enum EnumBarcodeFormat2 : Int{
    /** No barcode format in BarcodeFormat group 2 */
    NULL NS_SWIFT_NAME(Null) = 0x00
    /** Nonstandard barcode */
    NONSTANDARDBARCODE = 0x01
    /** PHARMACODE_ONE_TRACK */
    PHARMACODE_ONE_TRACK = 0x04
    /** PHARMACODE_ONE_TRACK */
    PHARMACODE_TWO_TRACK = 0x08
    /** PHARMACODE */
    PHARMACODE = 0x0C
    /** DotCode Barcode.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsMarks to EnumLocalizationMode if you don't set it,*/
    DOTCODE = 0x00000002
    /** Combined value of USPSINTELLIGENTMAIL, POSTNET, PLANET, AUSTRALIANPOST, RM4SCC.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    POSTALCODE = 0x01F00000
    /** USPS Intelligent Mail.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    USPSINTELLIGENTMAIL = 0x00100000
    /** Postnet.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    POSTNET = 0x00200000
    /** Planet.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    PLANET = 0x00400000
    /** Australian Post.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    AUSTRALIANPOST = 0x00800000
    /** Royal Mail 4-State Customer Barcode.
     When you set this barcode format, the library will automatically add EnumLocalizationModeStatisticsPostalCode to EnumLocalizationMode if you don't set it,*/
    RM4SCC = 0x01000000
}
```
