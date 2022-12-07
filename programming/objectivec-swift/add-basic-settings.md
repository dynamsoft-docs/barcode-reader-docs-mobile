---
layout: default-layout
title: Add Basic Settings - Dynamsoft Barcode Reader for iOS
description: This guide covers the basic settings for Dynamsoft Barcode Reader project for iOS. Find out how to add basic runtime settings to the iOS Barcode Reader project.
keywords: Guide, iOS, Settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/objectivec-swift/add-basic-settings.html
---

# Add Basic Settings

If you have followed the [Getting started](#user-guide.md), you may have managed to create a video streaming barcode reader project. In this article, you can learn about how to add basic runtime settings to your barcode reader project.

## Specify Barcode Formats

Specifying the barcode format is always the first step of barcode reader configuration. Be sure to confirm that the target barcode formats are included. Meanwhile, excluding the undesired barcodes will improve the processing efficiency. If you are not familiar with barcode format, the <a href="https://www.dynamsoft.com/barcode-types/barcode-types/" target="_blank">introduction of barcode formats</a> may help you understand it. Generally, the barcode format settings are updated via `PublicRuntimeSettings` class by specifying enumeration member of `BarcodeFormat` or `BarcodeFormat_2`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the current runtime settings
iPublicRuntimeSettings *settings = [barcodeReader getRuntimeSettings:nil];

// Change the settings that you want - in this case, the supported barcode formats
settings.barcodeFormatIds = EnumBarcodeFormatONED | EnumBarcodeFormatQRCODE;

// Call updateRuntimeSettings to update the settings object
[_barcodeReader updateRuntimeSettings:settings error:nil];
```
2. 
```swift
// Get the current runtime settings
let settings = try? barcodeReader.getRuntimeSettings()

// Change the settings that you want - in this case, the supported barcode formats
settings.barcodeFormatIds = EnumBarcodeFormat.ONED | EnumBarcodeFormat.QRCODE

// Call updateRuntimeSettings to update the settings object
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Set Barcode Count

The `expectedBarcodeCount` is the parameter that controls the number of expected results of the recognized barcodes via barcode reader from a single image. The process will be stopped as soon as the count of successfully decoded barcodes reaches the expected amount.

There are some suggestions on how to set the `expectedBarcodeCount`:

- When the app is designed to detect a **single** barcode per image or video frame, the recommended `expectedBarcodeCount` is **1**. This will sharply improve the processing speed.
- When there are **n** barcodes in a single image (**n** is a fixed number) and you'd like the barcode reader to decode **all of them**, the recommended `expectedBarcodeCount` is **n**.
- When the number of barcodes is unknown and you want to output **as many** barcode results as possible, you can set the `expectedBarcodeCount` to the **maximum possible value**.
- When the number of barcodes is unknown and you want to output **at least one** barcode result as soon as possible, you can set the `expectedBarcodeCount` to **0**. The barcode reader will try to decode at least one barcode from the image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Similar to the barcode format setting, you can update the barcode count setting via PublicRuntimeSettings.
iPublicRuntimeSettings *settings = [barcodeReader getRuntimeSettings:nil];

// Set the expected barcode count.
settings.expectedBarcodesCount = 1;

// You can update the barcode format settings together with the barcode count settings.
settings.barcodeFormatIds = EnumBarcodeFormatONED | EnumBarcodeFormatQRCODE;

// Update the settings
[_barcodeReader updateRuntimeSettings:settings error:nil];
```
2. 
```swift
// Similar to the barcode format setting, you can update the barcode count setting via PublicRuntimeSettings.
let settings = try? barcodeReader.getRuntimeSettings()

// Set the expected barcode count.
settings.expectedBarcodesCount = 1

// You can update the barcode format settings together with the barcode count settings.
settings.barcodeFormatIds = EnumBarcodeFormat.ONED | EnumBarcodeFormat.QRCODE

// Update the settings
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Define a Scan Region

It is not always necessary to scan the whole image to get the barcode result. You can define a scan region for your barcode reader to narrow the searching region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the DCE Camera view and add it to the main view
_dceView = [DCECameraView cameraWithFrame:self.view.bounds];
[self.view addSubview:_dceView];

// Initialize the DCE object using the DCE Camera View
_dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];

// You can update the barcode format settings together with the barcode count settings.
iRegionDefinition *scanRegion = [iRegionDefinition alloc];
scanRegion.regionTop = 25;
scanRegion.regionBottom = 75;
scanRegion.regionLeft = 25;
scanRegion.regionRight = 25;
scanRegion.regionMeasuredByPercentage = 1;

// Update the scan region for DCE
[_dce setScanRegion:scanRegion error:nil]
```
2. 
```swift
import DynamsoftCameraEnhancer

dceView = DCECameraView.init(frame: CGRect(x: 0, y: barHeight!, width: mainWidth, height: mainHeight - SafeAreaBottomHeight - barHeight!))
self.view.addSubview(dceView)
dce = DynamsoftCameraEnhancer.init(view: dceView)
let scanRegion = iRegionDefinition()
scanRegion.regionTop = 25
scanRegion.regionBottom = 75
scanRegion.regionLeft = 25
scanRegion.regionRight = 75
scanRegion.regionMeasuredByPercentage = 1
dce.setScanRegion(scanRegion, error:nil)
```

The above settings can meet the majority of usage scenarios. However, if the performance is still not satisfying, the following articles will help you on improving the performance.

- [Quick optimize performance](quick-performance-settings.md)

If you are facing license issues, the following pages might help you.

- [Licence Activation]({{ site.license_activation }})