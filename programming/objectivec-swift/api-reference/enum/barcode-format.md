---
layout: default-layout
title: BarcodeFormat - Dynamsoft Barcode Reader iOS Enumerations
description: The enumeration BarcodeFormat of Dynamsoft Barcode Reader iOS defines the supported barcode formats.
keywords: Barcode formats
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: BarcodeFormat
codeAutoHeight: true
---

# Enumeration BarcodeFormat

`BarcodeFormat` defines the supported barcode formats.

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_OPTIONS(NSUInteger , DSBarcodeFormat)
{
   /**No barcode format in BarcodeFormat*/
   DSBarcodeFormatNull = 0,
   /**All supported formats in BarcodeFormat .*/
   DSBarcodeFormatAll = 0xFFFFFFFEFFFFFFFF,
   DSBarcodeFormatDefault = 0xFE3BFFFF,
   /**Code 39*/
   DSBarcodeFormatCode39 = 1,
   /**Code 128*/
   DSBarcodeFormatCode128 = 1 << 1,
   /**Code 93*/
   DSBarcodeFormatCode93 = 1 << 2,
   /**Codabar*/
   DSBarcodeFormatCodabar = 1 << 3,
   /**Interleaved 2 of 5*/
   DSBarcodeFormatITF = 1 << 4,
   /**EAN-13*/
   DSBarcodeFormatEAN13 = 1 << 5,
   /**EAN-8*/
   DSBarcodeFormatEAN8 = 1 << 6,
   /**UPC-A*/
   DSBarcodeFormatUPCA = 1 << 7,
   /**UPC-E*/
   DSBarcodeFormatUPCE = 1 << 8,
   /**Industrial 2 of 5*/
   DSBarcodeFormatIndustrial25 = 1 << 9,
   /**CODE39 Extended*/
   DSBarcodeFormatCode39Extended = 1 << 10,
    /**DataBar Omnidirectional*/
   DSBarcodeFormatGS1DatabarOmniDirectional = 1 << 11,
    /**DataBar Truncated*/
   DSBarcodeFormatGS1DatabarTruncated = 1 << 12,
    /**DataBar Stacked*/
   DSBarcodeFormatGS1DatabarStacked = 1 << 13,
    /**DataBar Stacked Omnidirectional*/
   DSBarcodeFormatGS1DatabarStackedOmniDirectional = 1 << 14,
    /**DataBar Expanded*/
   DSBarcodeFormatGS1DatabarExpanded = 1 << 15,
    /**DataBar Expaned Stacked*/
   DSBarcodeFormatGS1DatabarExpandedStacked = 1 << 16,
    /**DataBar Limited*/
   DSBarcodeFormatGS1DatabarLimited = 1 << 17,
   /**Patch code.*/
   DSBarcodeFormatPatchCode = 1 << 18,
    /**Micro PDF417*/
   DSBarcodeFormatMicroPDF417 = 1 << 19,
   /**MSI Code*/
   DSBarcodeFormatMSICode = 1 << 20,
   /**CODE_11 .*/
   DSBarcodeFormatCode11 = 1 << 21,
   /**Decode barcode with 2 digital addons.*/
   DSBarcodeFormatTwoDigitAddOn = 1 << 22,
   /**Decode barcode with 5 digital addons.*/
   DSBarcodeFormatFiveDigitAddOn = 1 << 23,
   /**Code 32*/
   DSBarcodeFormatCode32 =  1L << 24,
   /**PDF417*/
   DSBarcodeFormatPDF417 = 1 << 25,
   /**QRCode*/
   DSBarcodeFormatQRCode = 1 << 26,
   /**DataMatrix*/
   DSBarcodeFormatDataMatrix = 1 << 27,
   /**AZTEC*/
   DSBarcodeFormatAztec = 1 << 28,
   /**MAXICODE*/
   DSBarcodeFormatMaxiCode = 1 << 29,
   /**Micro QR Code*/
   DSBarcodeFormatMicroQR = 1 << 30,
   /**GS1 Composite Code*/
   DSBarcodeFormatGS1Composite = 1 << 31,
   /**Combined value of BF_CODABAR, BF_CODE_128, BF_CODE_39, BF_CODE_39_Extended, BF_CODE_93, BF_EAN_13, BF_EAN_8, INDUSTRIAL_25, BF_ITF, BF_UPC_A, BF_UPC_E, BF_MSI_CODE*/
   DSBarcodeFormatOneD = 0x3007FF,
   /**Combined value of BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED*/
   DSBarcodeFormatGS1Databar = 0x3F800,
   DSBarcodeFormatNonStandardBarcode = 1 << 32,
   /**DotCode Barcode.
   When you set this barcode format, the library will automatically add DSLocalizationModeStatisticsMarks to LocalizationMode if you don't set it,*/
   DSBarcodeFormatDotCode = 1 << 33,
   /**PHARMACODE_ONE_TRACK*/
   DSBarcodeFormatPharmaCodeOneTrack = 1 << 34,
   /**PHARMACODE_ONE_TRACK*/
   DSBarcodeFormatPharmaCodeTwoTrack = 1 << 35,
   /**Matrix25.*/
   DSBarcodeFormatMatrix25 = 1L << 36,
   /**PHARMACODE*/
   DSBarcodeFormatPharmaCode = 0xC00000000,
   /**Combined value of DSBarcodeFormatUSPSINTELLIGENTMAIL, DSBarcodeFormatPOSTNET, DSBarcodeFormatPLANET, DSBarcodeFormatAUSTRALIANPOST, DSBarcodeFormatRM4SCC.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatPostalCode = 0x1F0000000000000,
   /**USPS Intelligent Mail.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatUSPSIntelligentMail = 1 << 52,
   /**Postnet.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatPostnet = 1 << 53,
   /**Planet.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatPlant = 1 << 54,
   /**Australian Post.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatAustralianPost = 1 << 55,
   /**Royal Mail 4-State Customer Barcode.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   DSBarcodeFormatRM4SCC = 1 << 56,
   /**Kix*/
   DSBarcodeFormatKix = 1L << 57,
   /**Telepen*/
   DSBarcodeFormatTelepen = 1L << 41,
   /**Telepen Numeric. A variation of the Telepen format optimized for encoding numeric data only.*/
   DSBarcodeFormatTelepenNumeric = 1L << 42,
   /**Combined value of BF2_USPSINTELLIGENTMAIL, BF2_POSTNET, BF2_PLANET, BF2_AUSTRALIANPOST, BF2_RM4SCC, BF_KIX.*/
   DSBarcodeFormatPostalCode = 0x3F0000000000000
};
```
>
```swift
public enum BarcodeFormat : Int
{
   /**No barcode format in BarcodeFormat*/
   Null = 0
   /**All supported formats in BarcodeFormat .*/
   all = 0xFFFFFFFEFFFFFFFF
   default = 0xFE3BFFFF
   /**Code 39*/
   code39 = 1
   /**Code 128*/
   code128 = 1 << 1
   /**Code 93*/
   code93 = 1 << 2
   /**Codabar*/
   codabar = 1 << 3
   /**Interleaved 2 of 5*/
   ITF = 1 << 4
   /**EAN-13*/
   EAN13 = 1 << 5
   /**EAN-8*/
   EAN8 = 1 << 6
   /**UPC-A*/
   UPCA = 1 << 7
   /**UPC-E*/
   UPCE = 1 << 8
   /**Industrial 2 of 5*/
   industrial25 = 1 << 9
   /**CODE39 Extended*/
   code39Extended = 1 << 10
   /**DataBar Omnidirectional*/
   gs1DatabarOmnidirectional = 1 << 11
   /**DataBar Truncated*/
   gs1DatabarTruncated = 1 << 12
   /**DataBar Stacked*/
   gs1DatabarStacked = 1 << 13
   /**DataBar Stacked Omnidirectional*/
   gs1DatabarStackedOmnidirectional = 1 << 14
   /**DataBar Expanded*/
   gs1DatabarExpanded = 1 << 15
   /**DataBar Expaned Stacked*/
   gs1DatabarExpandedStacked = 1 << 16
   /**DataBar Limited*/
   gs1DatabarLimited = 1 << 17
   /**Patch code.*/
   patchCode = 1 << 18
   /**Micro PDF417*/
   microPDF417 = 1 << 19
   /**MSI Code*/
   msiCode = 1 << 20
   /**CODE_11.*/
   code11 = 1 << 21
   /**Decode barcode with 2 digital addons.*/
   twoDigitAddOn = 1 << 22
   /**Decode barcode with 5 digital addons.*/
   fiveDigitAddOn = 1 << 23
   /**Code 32*/
   code32 =  1L << 24
   /**PDF417*/
   PDF417 = 1 << 25
   /**QRCode*/
   qrCode = 1 << 26
   /**DataMatrix*/
   dataMatrix = 1 << 27
   /**AZTEC*/
   aztec = 1 << 28
   /**MAXICODE*/
   maxiCode = 1 << 29
   /**Micro QR Code*/
   microQR = 1 << 30
   /**GS1 Composite Code*/
   gs1Composite = 1 << 31
   /**Combined value of BF_CODABAR, BF_CODE_128, BF_CODE_39, BF_CODE_39_Extended, BF_CODE_93, BF_EAN_13, BF_EAN_8, INDUSTRIAL_25, BF_ITF, BF_UPC_A, BF_UPC_E, BF_MSI_CODE*/
   oneD = 0x3007FF
   /**Combined value of BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED*/
   gs1Databar = 0x3F800,
   nonStandardBarcode = 1 << 32
   /**DotCode Barcode.
   When you set this barcode format, the library will automatically add DSLocalizationModeStatisticsMarks to LocalizationMode if you don't set it,*/
   dotCode = 1 << 33
   /**PHARMACODE_ONE_TRACK*/
   pharmaCodeOneTrack = 1 << 34
   /**PHARMACODE_ONE_TRACK*/
   pharmaCodeTwoTrack = 1 << 35
   /**Matrix25.*/
   matrix25 = 1L << 36
   /**PHARMACODE*/
   pharmaCode = 0xC00000000
   /**Combined value of DSBarcodeFormatUSPSINTELLIGENTMAIL, DSBarcodeFormatPOSTNET, DSBarcodeFormatPLANET, DSBarcodeFormatAUSTRALIANPOST, DSBarcodeFormatRM4SCC.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   postalCode = 0x1F0000000000000,
   /**USPS Intelligent Mail.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   uspsIntelligentMail = 1 << 52
   /**Postnet.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   postnet = 1 << 53
   /**Planet.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   planet = 1 << 54
   /**Australian Post.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   australianPost = 1 << 55
   /**Royal Mail 4-State Customer Barcode.
   When you set this barcode format, the library will automatically add LocalizationModeStatisticsPostalCode to LocalizationMode if you don't set it,*/
   RM4SCC = 1 << 56
   /**Kix*/
   kix = 1L << 57
   /**Telepen*/
   telepen = 1L << 41
   /**Telepen Numeric. A variation of the Telepen format optimized for encoding numeric data only.*/
   telepenNumeric = 1L << 42
   /**Combined value of BF2_USPSINTELLIGENTMAIL, BF2_POSTNET, BF2_PLANET, BF2_AUSTRALIANPOST, BF2_RM4SCC, BF_KIX.*/
   postalCode = 0x3F0000000000000
}
```
