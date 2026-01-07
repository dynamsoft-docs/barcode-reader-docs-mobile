---
layout: default-layout
title: LocalizationMode - Dynamsoft Barcode Reader iOS Enumerations
description: The enumeration LocalizationMode of Dynamsoft Barcode Reader iOS describes the localization modes of the barcodes.
keywords: Localization mode
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: LocalizationMode
codeAutoHeight: true
---

# Enumeration LocalizationMode

`LocalizationMode` specifies the strategies used to identify the locations of barcodes within an image.

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
typedef NS_ENUM(NSInteger , DSLocalizationMode)
{
   /**Not supported yet. */
   DSLocalizationModeAuto = 0x01,
   /**Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
   DSLocalizationModeConnectedBlocks = 0x02,
   /**Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
   DSLocalizationModeStatistics = 0x04,
   /**Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. */
   DSLocalizationModeLines = 0x08,
   /**Localizes barcodes quickly. This mode is recommended in interactive scenario. Check @ref LM for available argument settings.*/
   DSLocalizationModeScanDirectly = 0x10,
   /**Localizes barcodes by groups of marks.This is optimized for DPM codes. */
   DSLocalizationModeStatisticsMarks = 0x20,
   /**Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. */
   DSLocalizationModeStatisticsPostalCode = 0x40,
   /**Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
   DSLocalizationModeCentre = 0x80,
   /**Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
   DSLocalizationModeOneDFastScan = 0x100,
   /**Reserved setting for localization mode.*/
   DSLocalizationModeRev = -2147483648,
   /**Skips localization. */
   DSLocalizationModeSkip = 0x00,
   /**Localizes barcodes by utilizing a neural network model.*/
   DSLocalizationModeNeuralNetwork = 0x200,
   /**Placeholder value with no functional meaning.*/
   DSLocalizationModeEnd = 0xFFFFFFFF
};
```
>
```swift
public enum LocalizationMode : Int
{
   /**Not supported yet. */
   auto = 0x01
   /**Localizes barcodes by searching for connected blocks. This algorithm usually gives best result and it is recommended to set ConnectedBlocks to the highest priority. */
   connectedBlocks = 0x02
   /**Localizes barcodes by groups of contiguous black-white regions. This is optimized for QRCode and DataMatrix. */
   statistics = 0x04
   /**Localizes barcodes by searching for groups of lines. This is optimized for 1D and PDF417 barcodes. */
   lines = 0x08
   /**Localizes barcodes quickly. This mode is recommended in interactive scenario. Check @ref LM for available argument settings.*/
   scanDirectly = 0x10
   /**Localizes barcodes by groups of marks.This is optimized for DPM codes. */
   statisticsMarks = 0x20
   /**Localizes barcodes by groups of connected blocks and lines.This is optimized for postal codes. */
   postalCode = 0x40
   /**Localizes barcodes from the centre of the image. Check @ref LM for available argument settings. */
   centre = 0x80,
   /**Localizes 1D barcodes fast. Check @ref LM for available argument settings. */
   oneDFastScan = 0x100
   /**Reserved setting for localization mode.*/
   rev = -2147483648
   /**Skips localization. */
   skip = 0x00
   /**Localizes barcodes by utilizing a neural network model.*/
   neuralNetwork = 0x200
   /**Placeholder value with no functional meaning.*/
   end = 0xFFFFFFFF
}
```
