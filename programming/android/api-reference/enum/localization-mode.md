---
layout: default-layout
title: LocalizationMode - Dynamsoft Barcode Reader Android Enumerations
description: The enumeration LocalizationMode of Dynamsoft Barcode Reader Android describes the localization modes of the barcodes.
keywords: Localization mode
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: LocalizationMode
codeAutoHeight: true
---

# Enumeration LocalizationMode

`LocalizationMode` specifies the strategies used to identify the locations of barcodes within an image.

```java
@Retention(RetentionPolicy.CLASS)
public @interface EnumLocalizationMode {
   /**Not supported yet. */
   public static final int LM_AUTO = 1;
   /**Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
   public static final int LM_CONNECTED_BLOCKS = 2;
   /**Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
   public static final int LM_STATISTICS = 4;
   /**Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. */
   public static final int LM_LINES = 8;
   /**Localizes barcodes quickly. This mode is recommended in interactive scenario. Check @ref LM for available argument settings.*/
   public static final int LM_SCAN_DIRECTLY = 16;
   /**Localizes barcodes by groups of marks.This is optimized for DPM codes. */
   public static final int LM_STATISTICS_MARKS = 32;
   /**Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. */
   public static final int LM_STATISTICS_POSTAL_CODE = 64;
   /**Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
   public static final int LM_CENTRE = 128;
   /**Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
   public static final int LM_ONED_FAST_SCAN = 256;
   /**Skips localization. */
   public static final int LM_SKIP = 0;
   /**Reserved setting for localization mode. */
   public static final int LM_REV = 2147483648;
   /**Localizes barcodes with deep neural network algorithm. */
   public static final int LM_NEURAL_NETWORK = 0x200;
   /**Placeholder value with no functional meaning.*/
   public static final int LM_END = 0xFFFFFFFF;
}
```
