---
layout: default-layout
title: EnumBarcodeFormat
description: ThUse this enum data type to set constants for barcode format in your Dynamsoft Barcode Reader project.
keywords: EnumBarcodeFormat, BarcodeReader, api reference
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat
permalink: /programming/enumeration/barcode-format.html
---


# EnumBarcodeFormat

<div class="sample-code-prefix template2"></div>
   >- Android
   >- Objective-C
   >- Swift
   >
>
```java
public class EnumBarcodeFormat {
    public static final int BF_ALL = -29360129;
    public static final int BF_ONED = 3147775;
    public static final int BF_GS1_DATABAR = 260096;
    public static final int BF_NULL = 0;
    public static final int BF_CODE_39 = 1;
    public static final int BF_CODE_128 = 2;
    public static final int BF_CODE_93 = 4;
    public static final int BF_CODABAR = 8;
    public static final int BF_ITF = 16;
    public static final int BF_EAN_13 = 32;
    public static final int BF_EAN_8 = 64;
    public static final int BF_UPC_A = 128;
    public static final int BF_UPC_E = 256;
    public static final int BF_INDUSTRIAL_25 = 512;
    public static final int BF_CODE_39_EXTENDED = 1024;
    public static final int BF_GS1_DATABAR_OMNIDIRECTIONAL = 2048;
    public static final int BF_GS1_DATABAR_TRUNCATED = 4096;
    public static final int BF_GS1_DATABAR_STACKED = 8192;
    public static final int BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 16384;
    public static final int BF_GS1_DATABAR_EXPANDED = 32768;
    public static final int BF_GS1_DATABAR_EXPANDED_STACKED = 65536;
    public static final int BF_GS1_DATABAR_LIMITED = 131072;
    public static final int BF_PATCHCODE = 262144;
    public static final int BF_PDF417 = 33554432;
    public static final int BF_QR_CODE = 67108864;
    public static final int BF_DATAMATRIX = 134217728;
    public static final int BF_AZTEC = 268435456;
    public static final int BF_MAXICODE = 536870912;
    public static final int BF_MICRO_QR = 1073741824;
    public static final int BF_MICRO_PDF417 = 524288;
    public static final int BF_GS1_COMPOSITE = -2147483648;
    public static final int BF_MSI_CODE = 1048576;
    public static final int BF_CODE_11 = 2097152;
}
```
>
```objc
typedef NS_OPTIONS(NSInteger , EnumBarcodeFormat)
{
    /** No barcode format in BarcodeFormat group 1*/
    EnumBarcodeFormatNULL NS_SWIFT_NAME(Null) = 0x0,
    EnumBarcodeFormatCODE39 = 0x1,
    EnumBarcodeFormatCODE128 = 0x2,
    EnumBarcodeFormatCODE93 = 0x4,
    EnumBarcodeFormatCODABAR  = 0x8,
    /** Interleaved 2 of 5 */
    EnumBarcodeFormatITF = 0x10,
    EnumBarcodeFormatEAN13 = 0x20,
    EnumBarcodeFormatEAN8 = 0x40,
    EnumBarcodeFormatUPCA = 0x80,
    EnumBarcodeFormatUPCE = 0x100,
    EnumBarcodeFormatINDUSTRIAL = 0x200,
    EnumBarcodeFormatCODE39EXTENDED = 0x400,
    EnumBarcodeFormatMSICODE = 0x100000,
    EnumBarcodeFormatGS1DATABAROMNIDIRECTIONAL = 0x800,
    EnumBarcodeFormatGS1DATABARTRUNCATED = 0x1000,
    EnumBarcodeFormatGS1DATABARSTACKED = 0x2000,
    EnumBarcodeFormatGS1DATABARSTACKEDOMNIDIRECTIONAL = 0x4000,
    EnumBarcodeFormatGS1DATABAREXPANDED = 0x8000,
    EnumBarcodeFormatGS1DATABAREXPANDEDSTACKED = 0x10000,
    EnumBarcodeFormatGS1DATABARLIMITED = 0x20000,
    EnumBarcodeFormatPATCHCODE = 0x00040000,
    EnumBarcodeFormatCODE_11 = 0x200000,
    EnumBarcodeFormatPDF417 = 0x02000000,
    EnumBarcodeFormatQRCODE = 0x04000000,
    EnumBarcodeFormatDATAMATRIX = 0x08000000,
    EnumBarcodeFormatAZTEC = 0x10000000,
    EnumBarcodeFormatMAXICODE = 0x20000000,
    EnumBarcodeFormatMICROQR = 0x40000000,
    EnumBarcodeFormatMICROPDF417 = 0x00080000,
    EnumBarcodeFormatGS1COMPOSITE = -2147483648,
    /** Combined value of all oneD barcodes */
    EnumBarcodeFormatONED = 0x003007FF,
    /** Combined value of all GS1_DATABAR */
    EnumBarcodeFormatGS1DATABAR = 0x0003F800,
    /** All supported formats in BarcodeFormat group 1. */
    EnumBarcodeFormatALL = -29360129
};
```
>
```swift
public enum EnumBarcodeFormat : Int{
    /** No barcode format in BarcodeFormat group 1*/
    Null = 0x0
    CODE39 = 0x1
    CODE128 = 0x2
    CODE93 = 0x4
    CODABAR  = 0x8
    /** Interleaved 2 of 5 */
    ITF = 0x10
    EAN13 = 0x20
    EAN8 = 0x40
    UPCA = 0x80
    UPCE = 0x100
    INDUSTRIAL = 0x200
    CODE39EXTENDED = 0x400
    MSICODE = 0x100000
    GS1DATABAROMNIDIRECTIONAL = 0x800
    GS1DATABARTRUNCATED = 0x1000
    GS1DATABARSTACKED = 0x2000
    GS1DATABARSTACKEDOMNIDIRECTIONAL = 0x4000
    GS1DATABAREXPANDED = 0x8000
    GS1DATABAREXPANDEDSTACKED = 0x10000
    GS1DATABARLIMITED = 0x20000
    PATCHCODE = 0x00040000
    CODE_11 = 0x200000
    PDF417 = 0x02000000
    QRCODE = 0x04000000
    DATAMATRIX = 0x08000000
    AZTEC = 0x10000000
    MAXICODE = 0x20000000
    MICROQR = 0x40000000
    MICROPDF417 = 0x00080000
    GS1COMPOSITE = -2147483648
    /** Combined value of CODABAR, CODE128, CODE39, CODE39Extended, CODE93, EAN13, EAN8, INDUSTRIAL25, ITF, UPCA, UPCE, MSICODE, CODE_11*/
    ONED = 0x003007FF
    /** Combined value of all GS1 Databar*/
    GS1DATABAR = 0x0003F800
    /** All supported formats in BarcodeFormat group 1. */
    ALL = -29360129
}
```
