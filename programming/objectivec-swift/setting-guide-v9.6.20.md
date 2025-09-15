---
layout: default-layout
title: Advanced Usage - Dynamsoft Barcode Reader for iOS
description: This guide helps you initialize, optimize, & reset the barcode decoding settings for your iOS barcoding reading project.
keywords: Guide, iOS, Settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/objectivec-swift/setting-guide-v9.6.20.html
---

# Configure Runtime Settings

`iPublicRuntimeSettings` is the struct that includes the majority of available barcode decoding settings. There is a series of methods for you to get, optimize or even reset the settings. On this page, you will be guided on how to initialize, optimize or reset the barcode decoding settings.

## Initialize Settings

You can initialize the parameter settings for your iOS barcode reader with a template or simply start with the default settings. When the template is added to the project, you can still add additional settings to the project to further optimize the performance of the barcode reader to cover your requirements.

### Initialize with Preset Template

The preset templates are listed as follow:

| Template Name | Description |
| ------------- | ----------- |
| `EnumPresetTemplateDefault` | Reset to default barcode decoding parameters. |
| `EnumPresetTemplateVideoSingleBarcode` | Switch to single barcode decoding template. The parameter settings will be optimized to reach a higher speed on processing single barcode. |
| `EnumPresetTemplateVideoSpeedFirst` | Switch to speed first template for video streaming barcode decoding. The barcode processing speed will be improved for the majority of video barcode decoding scenarios. |
| `EnumPresetTemplateVideoReadRateFirst` | Switch to speed first template for image barcode decoding. The barcode processing speed will be improved for the majority of video barcode decoding scenarios. |
| `EnumPresetTemplateImageSpeedFirst` | Switch to read rate first template for video streaming barcode decoding. The barcode reader will be able to successfully decode on the majority of barcodes when decoding from the video streaming. |
| `EnumPresetTemplateImageReadRateFirst` | Switch to read rate first template for image barcode decoding. The barcode reader will be able to successfully decode as many barcodes as possible from a single image. |

The preset templates can be update via method [`updateRuntimeSettings`](api-reference/primary-parameter-and-runtime-settings-basic.html#with-a-preset-template). When a new template is selected, all the previous barcode parameter settings are reset to the newly select template values.

### Initialize with Customized Template

Dynamsoft Technical Support can help you on providing a customized barcode decoding template. Feel free to <a href="https://www.dynamsoft.com/Company/Contact.aspx" target="_blank">contact us</a> when:

- The performance is not satisfying.
- The templates are puzzling
- You have specific requirements on the performance

The template will be a JSON data that can be uploaded via method `initRuntimeSettingsWithFile` and `initRuntimeSettingsWithString`. Similar with the preset templates, you can add additional settings to optimize the performance. The following information will help us provide you with a better template.

- The targeting barcode formats.
- The device information (hardware model, software version).
- The barcode scanning distance.
- Sample image or video for the usage scenarios.

```objc
NSError __autoreleasing * _Nullable error;
[barcodeReader initRuntimeSettingsWithString:@"{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}" conflictMode:EnumConflictModeOverwrite error:&error];
```

## Optimize Settings

The templates are designed to simplify the parameter settings. It might not cover the requirements. Modes parameters and other settings like barcode formats are available in the `iPublicRuntimeSettings` class. You can use the following steps to change the settings. When you update the settings, only the newly configured settings will be changed and the other settings will remain the same.

**Step 1. getRuntimeSettings**

Use the following code to get the current settings.

```objc
iPublicRuntimeSettings *runtimeSettings = [_barcodeReader getRuntimeSettings:&settingsError];
```

The `runtimeSettings` you got from `getRuntimeSettings` is an object of `iPublicRuntimeSettings`. In the object, there are the settings you previously updated via templates. You can view and directly change the parameter values in the `iPublicRuntimeSettings` object.

**Step 2. Optimize the required settings**

Since you have got the `runtimeSettings`, you can add the following code to change the settings in the object. Here, `barcodeFormats` and `LocalizationModes` will be illustrated as an example for optimizing the settings.

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
