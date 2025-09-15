---
layout: default-layout
title: Read-Rate-First Settings Samples - Dynamsoft Barcode Reader for iOS
description: This is the Read-Rate-First Settings Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, speed
needAutoGenerateSidebar: true
breadcrumbText: ReadRateFirstSettings
permalink: /programming/objectivec-swift/samples/read-rate.html
---

# ReadRateFirstSettings Sample

The Read-Rate-First Settings Sample illustrates how to maximize the rate when using Dynamsoft Barcode Reader iOS SDK. Generally, the Read Rate of a barcode reader refers to the rate of successfully recognized barcode among all barcodes in the given image in one scan.

**View Samples (on GitHub)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v8.8.0/ios/Objective-C/Performance/ReadRateFirstSettingsObjC/" target="_blank">Objective-C Read-Rate-First Settings Sample (v8.8.0)</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v8.8.0/ios/Swift/Performance/ReadRateFirstSettingsSwift/" target="_blank">Swift Read-Rate-First Settings Sample (v8.8.0)</a>

## Regular Settings

### The Region Definition

It is not recommended to make configurations on the scan region if the app is focusing on improving the Read-Rate. Dynamsoft Barcode Reader iOS SDK will scan the full image by default.

### The Format Specification

The barcode formats can be specified via [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html). The default value of DBR is not supporting all available barcode formats. Optimizing the barcode format settings to cover the requirements will help you to create a high-efficiency and high-read-rate barcode reader that covers your usage scenario.

**Related APIs**

- View class [`PublicRuntimeSettings`]({{ site.oc_api }}auxiliary-iPublicRuntimeSettings.html) to learn about the default barcode formats.
- View Enum [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) to learn about all available barcode formats.

### The Barcode Count

The barcode count setting determines the maximum barcodes the barcode reader can recognize at once from a single image/frame. Increasing the expected barcode count benefits the read rate but declines the reading speed at the same time.

## Modes Parameter Settings

Suppose the barcode format and the barcode count are completely set. The main factors that determine the read rate are how to localize as many barcodes as possible and how to recognize all the localized barcodes.

### Localization Friendly Parameters

The following pre-processing modes parameter settings will benefit the localization process. The barcode reader always tries different parameter combinations to find as many barcodes as the pre-set value. Despite the influence on processing speed, pre-set more parameters will definitely improve the read rate of your barcode reader.

| Modes Parameter | Description |
| --------------- | ----------- |
| [`ColourConversionModes`]({{ site.parameters_reference }}colour-conversion-modes.html) | Convert the coloured image into grayscale image. |
| [`GrayscaleTransformationModes`]({{ site.parameters_reference }}grayscale-transformation-modes.html) | Switch between the original and invert image when processing the grayscale images. |
| [`RegionPredetectionModes`]({{ site.parameters_reference }}region-predetection-modes.html) | Algorithm that pre-detect the barcode region. |
| [`ImagePreprocessingModes`]({{ site.parameters_reference }}image-preprocessing-modes.html) | Pre-processing on the barcodes for different scenarios. |
| [`BinarizationModes`]({{ site.parameters_reference }}binarization-modes.html) | Pre-processing on the barcodes by binarization. |
| [`LocalizationModes`]({{ site.parameters_reference }}localization-modes.html) | The modes that applied to localize the barcode. |

### Barcode Reading Friendly Parameters

The following parameters will benefit the barcode decoding.

| Modes Parameter | Description |
| --------------- | ----------- |
| [`ScaleUpModes`]({{ site.parameters_reference }}scale-up-modes.html) | Enhance the read rate of small sized barcodes. |
| [`DeformationResistingModes`]({{ site.parameters_reference }}deformation-resisting-modes.html) | Enhance the read rate of deformed barcodes (QR & DataMatrix barcodes only). |
| [`DeblurModes`]({{ site.parameters_reference }}deblur-modes.html) | Enhance the read rate when processing a blurry image. |
| [`MirrorMode`]({{ site.parameters_reference }}mirror-mode.html) | Try decoding by mirroring the barcodes. |
| [`DPMCodeReadingModes`]({{ site.parameters_reference }}dpm-code-reading-modes.html) | Enhance the recognition of DPM barcodes. |
