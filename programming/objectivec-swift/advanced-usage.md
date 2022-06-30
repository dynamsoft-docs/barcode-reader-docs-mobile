---
layout: default-layout
title: Dynamsoft Barcode Reader for iOS - Advanced Usage
description: This is the Advanced Usage page of Dynamsoft Barcode Reader for iOS SDK.
keywords: Guide, iOS, Settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/objectivec-swift/advanced-usage.html
---

# Advanced Usage

If you have followed the [Getting started](user-guide.md), you may have managed to create a video streaming barcode reader project. In this article, you can learn about how to use the runtime settings of the SDK to further improve the performance or deal with certain user scenarios. Throughout this guide, we will present some of these user scenarios and how you can use the runtime settings to deal with them. First, we will start with what the runtime settings are and how they are set.

<span style="font-size:20px">Table of Contents</span>

* [What are Runtime Settings?](#what-are-runtime-settings)
    * [Initialize Settings](#initialize-settings)
        * [Initialize with Preset Template](#initialize-with-preset-template)
        * [Initialize with Customized Template](#initialize-with-customized-template)
    * [Optimize Settings](#optimize-settings)
* [Various User Scenarios](#various-usage-scenarios)
    * [Specify Supported Barcode Formats](#specify-supported-barcode-formats)
    * [Set Expected Barcode Count](#set-expected-barcode-count)
    * [Define a Scan Region](#define-a-scan-region)

## What are Runtime Settings?

>Note:
> It is recommended to complete the [`Getting Started`](user-guide.md) page before you start configuring the runtime settings.

`iPublicRuntimeSettings` is the struct that includes the majority of available barcode decoding settings. There is a series of methods for you to get, optimize or even reset the settings. On this page, you will be guided on how to initialize, optimize or reset the barcode decoding settings.

### Initialize Settings

You can initialize the parameter settings for your Android barcode reader with a template or simply start with the default settings. When the template is added to the project, you can still add additional settings to further optimize the performance of the barcode reader and meet your requirements.

#### Initialize with Preset Template

The preset templates are listed as follow:

| Template Name | Description |
| ------------- | ----------- |
| `DEFAULT` | Reset to default barcode decoding parameters. |
| `VIDEO_SINGLE_BARCODE` | Switch to single barcode decoding template. The parameter settings will be optimized to reach a higher speed on processing single barcode. |
| `VIDEO_SPEED_FIRST` | Switch to speed first template for video streaming barcode decoding. The barcode processing speed will be improved for the majority of video barcode decoding scenarios. |
| `IMAGE_SPEED_FIRST` | Switch to speed first template for image barcode decoding. The barcode processing speed will be improved for the majority of video barcode decoding scenarios. |
| `VIDEO_READ_RATE_FIRST` | Switch to read rate first template for video streaming barcode decoding. The barcode reader will be able to successfully decode on the majority of barcodes when decoding from the video streaming. |
| `IMAGE_READ_RATE_FIRST` | Switch to read rate first template for image barcode decoding. The barcode reader will be able to successfully decode as many barcodes as possible from a single image. |

The preset templates can be update via method [`updateRuntimeSettings`](api-reference/primary-parameter-and-runtime-settings-basic.md#with-a-preset-template). When a new template is selected, all the previous barcode parameter settings are reset to the newly select template values.

#### Initialize with Customized Template

Dynamsoft Technical Support can help you on providing a customized barcode decoding template. Feel free to <a href="https://www.dynamsoft.com/Company/Contact.aspx" target="_blank">contact us</a> when:

- The performance is not satisfactory
- The templates are puzzling
- Specific requirements on the performance have not been met

The template will be a JSON file/string that can be uploaded via method `initRuntimeSettingsWithFile` and `initRuntimeSettingsWithString`. Similar to the preset templates, you can add additional settings to optimize the performance. The following information will help us provide you with a better template.

- Which barcode format(s) do you want to support?
- What type of devices will be used? (hardware model, software version).
- How long are the barcodes from the camera?
- Do you have a sample image or video for the usage scenarios that you can share with the team?

```objc
NSError __autoreleasing * _Nullable error;
[barcodeReader initRuntimeSettingsWithString:@"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}" conflictMode:EnumConflictModeOverwrite error:&error];
```

### Optimize Settings

The templates are designed to simplify the parameter settings. It might not cover all the requirements, however. Modes parameters and other settings like barcode formats are available in the `iPublicRuntimeSettings` class. You can use the following steps to change the settings. When you update the settings, only the newly configured settings will be changed and the other settings will remain the same.

**Step 1. getRuntimeSettings**

Use the following code to get the current settings.

```objc
iPublicRuntimeSettings *runtimeSettings = [_barcodeReader getRuntimeSettings:&settingsError];
```

The `runtimeSettings` you got from `getRuntimeSettings` is an object of `iPublicRuntimeSettings`. In the object, there are the settings you previously updated via templates. You can view and directly change the parameter values in the `iPublicRuntimeSettings` object.

**Step 2. Optimize the required settings**

Since you have got the `runtimeSettings`, you can add the following code to change the settings in the object. Here, `BarcodeFormats` and `LocalizationModes` will be illustrated as an example for optimizing the settings.

```objc
iPublicRuntimeSettings *runtimeSettings = [_barcodeReader getRuntimeSettings:&settingsError];

// You can specify the barcode formats via runtime settings.
runtimeSettings.barcodeFormatIds = EnumBarcodeFormatALL;

// LocalizationModes is the modes parameter that controls how the barcodes will be located.
// Localization mode "scan directly" and "connected blocks" are enabled here.
// You can enable at most 8 modes for each modes parameter.
runtimeSettings.LocalizationModes = @[@(EnumLocalizationModeScanDirectly), @(EnumLocalizationModeConnectedBlocks)];
```

**Step 3. updateRuntimeSettings**

When you have already completed the settings, you can update the settings via the method `updateRuntimeSettings`. All the settings you have configured will be updated to the barcode reader and the other settings will remain the same.

```objc
iPublicRuntimeSettings *runtimeSettings = [_barcodeReader getRuntimeSettings:&settingsError];
runtimeSettings.barcodeFormatIds = EnumBarcodeFormatALL;
runtimeSettings.LocalizationModes = @[@(EnumLocalizationModeScanDirectly), @(EnumLocalizationModeConnectedBlocks)];
// Update all above settings.
[_barcodeReader updateRuntimeSettings:runtimeSettings error:&settingsError];
```

Please note, when there exists an invalid value in the `runtimeSetting` object you want to update, none of the settings are updated.

# Various Usage Scenarios

If you have followed the [Getting started](#user-guide.md), you may have managed to create a video streaming barcode reader project. In this article, you can learn about how to add basic runtime settings to your barcode reader project.

## Specify Barcode Formats

Specifying the barcode format is always the first step of barcode reader configuration. Be sure to confirm that the target barcode formats are included. Meanwhile, excluding the undesired barcodes will improve the processing efficiency. If you are not familiar with barcode format, the <a href="https://www.dynamsoft.com/barcode-types/barcode-types/" target="_blank">introduction of barcode formats</a> may help you understand it. Generally, the barcode format settings are updated via `iPublicRuntimeSettings` class by specifying enumeration member of `BarcodeFormat` or `BarcodeFormat_2`.

```swift
// First step, get the instance of setting
// You can either get the instance from current settings or create a new instance.
let settings = try? barcodeReader.getRuntimeSettings()

// Second step, update the settings of barcodeFormatIds.
// There are two groups of barcode formats, BarcodeFormat and BarcodeFormat_2
// The Majority of common barcodes like oneD barcode and QR code are stored in the first group of barcode format.
// Some of the enumeration members are combined value of a group of barcodes like BF_ONED and BF_GS1_DATABAR
// Use "|" to enable multiple barcode formats at one time.
settings.barcodeFormatIds = EnumBarcodeFormat.ONED | EnumBarcodeFormat.QRCODE

// Update the settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Set Barcode Count

The `expectedBarcodeCount` is the parameter that controls the number of expected results of the recognized barcodes via barcode reader from a single image. The process will be stopped as soon as the count of successfully decoded barcodes reaches the expected amount.

There are some suggestions on how to set the `expectedBarcodeCount`:

- When your project is design for decoding **single** barcode, the recommended `expectedBarcodeCount` is **1**. This will sharply improve the processing speed.
- When there are **n** barcodes in a single image (**n** is a fixed number) and you'd like the barcode reader to decode **all of them**, the recommended `expectedBarcodeCount` is **n**.
- When the number of barcodes is unknown and you want to output **as many** barcode results as possible, you can set the `expectedBarcodeCount` to the **maximum possible count**.
- When the number of barcodes is unknown and you want to output **at least one** barcode result as soon as possible, you can set the `expectedBarcodeCount` to **0**. The barcode reader will try to decode at least one barcode from the image.

```swift
// Similar to the barcode format setting, you can update the barcode count setting via iPublicRuntimeSettings.
let settings = try? barcodeReader.getRuntimeSettings()

// Set the expected barcode count.
settings.expectedBarcodesCount = 1

// You can update the barcode format settings together with the barcode count settings.
settings.barcodeFormatIds = EnumBarcodeFormat.ONED | EnumBarcodeFormat.QRCODE

// Update the settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Define a Scan Region

It is not always necessary to scan the whole image to get the barcode result. You can define a scan region for your barcode reader to narrow the searching region.

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

The above settings can meet the majority of usage scenarios. However, if the performance is still not at a satisfactory level, the following articles can help you.

- [Optimizing Performance](quick-performance-settings.md)
- [UI Configuration](ui-configurations.md)

If you are facing license issues, the following page might help you.

- [Licence Activation]({{ site.license_activation }})
