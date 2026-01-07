---
layout: default-layout
title: BarcodeFormat - Dynamsoft Barcode Reader Android Enumerations
description: The enumeration BarcodeFormat of Dynamsoft Barcode Reader Android defines the supported barcode formats.
keywords: Barcode formats
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: BarcodeFormat
codeAutoHeight: true
---

# Enumeration BarcodeFormat

`BarcodeFormat` defines the supported barcode formats.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumBarcodeFormat {
   /**All supported formats in BarcodeFormat.*/
   public static final long BF_ALL = 0xFFFFFFFEFFFFFFFF;
   /**The default settings.*/
   public static final long BF_DEFAULT = 0xFE3BFFFFL;
   /**Combined value of BF_CODABAR, BF_CODE_128, BF_CODE_39, BF_CODE_39_Extended, BF_CODE_93, BF_EAN_13, BF_EAN_8, INDUSTRIAL_25, BF_ITF, BF_UPC_A, BF_UPC_E, BF_MSI_CODE.*/
   public static final long BF_ONED = 0x3007FFL;
   /**Combined value of BF_GS1_DATABAR_OMNIDIRECTIONAL, BF_GS1_DATABAR_TRUNCATED, BF_GS1_DATABAR_STACKED, BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL, BF_GS1_DATABAR_EXPANDED, BF_GS1_DATABAR_EXPANDED_STACKED, BF_GS1_DATABAR_LIMITED*/
   public static final long BF_GS1_DATABAR = 0x3F800L;
   /**Disable all barcode format.*/
   public static final long BF_NULL = 0L;
   /**Code 39.*/
   public static final long BF_CODE_39 = 1L << 0;
   /**Code 128.*/
   public static final long BF_CODE_128 = 1L << 1;
   /**Code 93.*/
   public static final long BF_CODE_93 = 1L << 2;
   /**Codabar.*/
   public static final long BF_CODABAR = 1L << 3;
   /**Interleaved 2 of 5.*/
   public static final long BF_ITF = 1L << 4;
   /**EAN 13.*/
   public static final long BF_EAN_13 = 1L << 5;
   /**EAN_8 barcode.*/
   public static final long BF_EAN_8 = 1L << 6;
   /**UPC_A barcode.*/
   public static final long BF_UPC_A = 1L << 7;
   /**UPC_E barcode.*/
   public static final long BF_UPC_E = 1L << 8;
   /**Industrial 25 barcode*/
   public static final long BF_INDUSTRIAL_25 = 1L << 9;
   /**Code 39 Extended.*/
   public static final long BF_CODE_39_EXTENDED = 1L << 10;
   /**GS1 Databar - Omnidirectional.*/
   public static final long BF_GS1_DATABAR_OMNIDIRECTIONAL = 1L << 11;
   /**GS1 Databar - Truncated.*/
   public static final long BF_GS1_DATABAR_TRUNCATED = 1L << 12;
   /**GS1 Databar - Stacked.*/
   public static final long BF_GS1_DATABAR_STACKED = 1L << 13;
   /**GS1 Databar - Stacked omnidirectional.*/
   public static final long BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 1L << 14;
   /**GS1 Databar - Expanded.*/
   public static final long BF_GS1_DATABAR_EXPANDED = 1L << 15;
   /**GS1 Databar - Expanded stacked.*/
   public static final long BF_GS1_DATABAR_EXPANDED_STACKED = 1L << 16;
   /**GS1 Databar - Limited.*/
   public static final long BF_GS1_DATABAR_LIMITED = 1L << 17;
   /**Patch code.*/
   public static final long BF_PATCHCODE = 1L << 18;
   /**Micro PDF417 barcode.*/
   public static final long BF_MICRO_PDF417 = 1L << 19;
   /**MSI code.*/
   public static final long BF_MSI_CODE = 1L << 20;
   /**Code 11.*/
   public static final long BF_CODE_11 = 1L << 21;
   /**Decode barcode with 2 digital addons.*/
   public static final long BF_TWO_DIGIT_ADD_ON = 1L << 22,
   /**Decode barcode with 5 digital addons.*/
   public static final long BF_FIVE_DIGIT_ADD_ON = 1L << 23,
   /**Code 32*/
   public static final long BF_CODE_32 =  1L << 24;
   /**PDF417 barcode.*/
   public static final long BF_PDF417 = 1L << 25;
   /**QR code.*/
   public static final long BF_QR_CODE = 1L << 26;
   /**Data matrix.*/
   public static final long BF_DATAMATRIX = 1L << 27;
   /**AZTEC barcode.*/
   public static final long BF_AZTEC = 1L << 28;
   /**Maxicode.*/
   public static final long BF_MAXICODE = 1L << 29;
   /**Micro QR Code.*/
   public static final long BF_MICRO_QR = 1L << 30;
   /**GS1 Composite Code.*/
   public static final long BF_GS1_COMPOSITE = 1L << 31;
   /**Nonstandard barcode.*/
   public static final long BF_NONSTANDARD_BARCODE = 1L << 32;
   /**Dotcode.*/
   public static final long BF_DOTCODE = 1L << 33;
   /**Pharma code.*/
   public static final long BF_PHARMACODE = 0xC00000000L;
   /**Pharma code with one track.*/
   public static final long BF_PHARMACODE_ONE_TRACK = 1L << 34;
   /**Pharma code with two track.*/
   public static final long BF_PHARMACODE_TWO_TRACK = 1L << 35;
   /**Matrix25.*/
   public static final long BF_MATRIX_25 = 1L << 36;
   /**Combined value of BF_USPSINTELLIGENTMAIL, BF_POSTNET, BF_PLANET, BF_AUSTRALIANPOST, BF_RM4SCC, BF_KIX.*/
   public static final long BF_POSTALCODE = 0x3F0000000000000;
   /**USPS Intelligent Mail barcode.*/
   public static final long BF_USPSINTELLIGENTMAIL = 1L << 52;
   /**Postnet barcode.*/
   public static final long BF_POSTNET = 1L << 53;
   /**Planet barcode.*/
   public static final long BF_PLANET = 1L << 54;
   /**Australian post barcode.*/
   public static final long BF_AUSTRALIANPOST = 1L << 55;
   /**Royal Mail 4-State Customer barcode.*/
   public static final long BF_RM4SCC = 1L << 56;
   /**Kix.*/
   public static final long BF_KIX = 1L << 57;
   /**Telepen*/
   public static final long BF_TELEPEN = 1L << 41;
   /**Telepen Numeric. A variation of the Telepen format optimized for encoding numeric data only.*/
   public static final long BF_TELEPEN_NUMERIC = 1L << 42;
}
```
