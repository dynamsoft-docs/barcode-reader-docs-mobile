---
layout: default-layout
title: Dynamsoft Barcode Reader for Android - Advanced Usage
description: This is the Advanced Usage page of Dynamsoft Barcode Reader for Android SDK.
keywords: Guide, Android, Settings
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/advanced-usage.html
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

`PublicRuntimeSettings` is the struct that includes the majority of available barcode decoding settings. There is a series of methods for you to get, optimize or even reset the settings. On this page, you will be guided on how to initialize, optimize or reset the barcode decoding settings.

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

Dynamsoft's technical support team can help you in coming up with a customized barcode decoding template. Feel free to <a href="https://www.dynamsoft.com/Company/Contact.aspx" target="_blank">contact us</a> when:

- The performance is not satisfactory
- The templates are puzzling
- Specific requirements on the performance have not been met

The template will be a JSON file/string that can be uploaded via the methods `initRuntimeSettingsWithFile` or `initRuntimeSettingsWithString`. Similar to the preset templates, you can configure additional settings to optimize the performance once the initialization is complete. The following information will help us provide you with a better template.

- Which barcode format(s) do you want to support?
- What type of devices will be used? (hardware model, software version).
- How long are the barcodes from the camera?
- Do you have a sample image or video for the usage scenarios that you can share with the team?

```java
BarcodeReader reader = new BarcodeReader();
// Input a stringified JSON data in the method to initialize the template.
// You can set whether to inherit or overwrite the previous settings.
reader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", EnumConflictMode.CM_OVERWRITE);
```

### Optimize Settings

The templates are designed to simplify the parameter settings. It might not cover all the requirements, however. Modes parameters and other settings like barcode formats are available in the `PublicRuntimeSettings` class. You can use the following steps to change the settings. When you update the settings, only the newly configured settings will be changed and the other settings will remain the same.

**Step 1. getRuntimeSettings**

Use the following code to get the current settings.

```java
PublicRuntimeSettings runtimeSettings = barcodeReader.getRuntimeSettings();
```

The `runtimeSettings` you got from `getRuntimeSettings` is an object of `PublicRuntimeSettings`. In the object, there are the settings you previously updated via templates. You can view and directly change the parameter values in the `PublicRuntimeSettings` object.

**Step 2. Optimize the required settings**

Since you have got the `runtimeSettings`, you can add the following code to change the settings in the object. Here, `BarcodeFormats` and `LocalizationModes` will be illustrated as an example for optimizing the settings.

```java
PublicRuntimeSettings runtimeSettings = barcodeReader.getRuntimeSettings();

// You can specify the barcode formats via runtime settings.
runtimeSettings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE;

// LocalizationModes is the modes parameter that controls how the barcodes will be located.
// Localization mode "scan directly" and "connected blocks" are enabled here.
// You can enable at most 8 modes for each modes parameter.
runtimeSettings.localizationModes = new int[]{EnumLocalizationMode.LM_SCAN_DIRECTLY,EnumLocalizationMode.LM_CONNECTED_BLOCKS};
```

**Step 3. updateRuntimeSettings**

When you have already completed the settings, you can update the settings via the method `updateRuntimeSettings`. All the settings you have configured will be updated to the barcode reader and the other settings will remain the same.

```java
PublicRuntimeSettings runtimeSettings = barcodeReader.getRuntimeSettings();
runtimeSettings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE;
runtimeSettings.localizationModes = new int[]{EnumLocalizationMode.LM_SCAN_DIRECTLY,EnumLocalizationMode.LM_CONNECTED_BLOCKS};
// Update all above settings.
reader.updateRuntimeSettings(runtimeSettings);
```

Please note, when there exists an invalid value in the `runtimeSetting` object you want to update, none of the settings are updated.

## Various Usage Scenarios

In this next section, we will present some of the most common scenarios that DBR users encounter when trying to customize the settings. For reference, this is only a fraction of the popular sceanrios we've encountered. If you are interested in learning more of those scenarios, please refer to <a href="https://www.dynamsoft.com/barcode-reader/parameters/scenario-settings/?ver=latest" target="_blank">this page</a>.

### Specify Supported Barcode Formats

Specifying the supported barcode format(s) is usually the most popular ask that our users have. Firstly, be sure to confirm that the target barcode formats are supported by the SDK. In addition, excluding the undesired barcodes will improve the processing efficiency. If you are not familiar with the full list of barcode formats, the <a href="https://www.dynamsoft.com/barcode-types/barcode-types/" target="_blank">introduction of barcode formats</a> will help you get quickly acclimated. Generally, the barcode format settings are updated via the `barcodeFormatIds` and `barcodeFormatIds_2` members of the `PublicRuntimeSettings` class.

```java
// Create an instance of PublicRuntimeSettings.
// You can update basic settings via PublicRuntimeSettings class.
PublicRuntimeSettings settings = reader.getRuntimeSettings();

// Specify the barcode formats by enumeration values.
// The first group of barcode format (barcodeFormatIds) contains the majority of common barcode formats.
// Some special formats are listed in the second group (BarcodeFormatIds_2).
settings.barcodeFormatIds = EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_ONED;

// Update the configured settings.
reader.updateRuntimeSettings(settings);
```

### Set Expected Barcode Count

The `expectedBarcodeCount` is the parameter that controls the number of expected results of the recognized barcodes via barcode reader from a single image. The process will be stopped as soon as the count of successfully decoded barcodes reaches the expected amount.

There are some suggestions on how to set the `expectedBarcodeCount`:

- When your project is design for decoding **single** barcode, the recommended `expectedBarcodeCount` is **1**. This will sharply improve the processing speed.
- When there are **n** barcodes in a single image (**n** is a fixed number) and you'd like the barcode reader to decode **all of them**, the recommended `expectedBarcodeCount` is **n**.
- When the number of barcodes is unknown and you want to output **as many** barcode results as possible, you can set the `expectedBarcodeCount` to the **maximum possible count**.
- When the number of barcodes is unknown and you want to output **at least one** barcode result as soon as possible, you can set the `expectedBarcodeCount` to **0**. The barcode reader will try to decode at least one barcode from the image.

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();

// Set the expected barcode count
settings.expectedBarcodesCount = 0;
reader.updateRuntimeSettings(settings);
```

### Define a Scan Region

It is not always necessary to scan the whole image to get the barcode result. You can define a scan region for your barcode reader to narrow the searching region.

```java
import com.dynamsoft.dce.CameraEnhancer;

RegionDefinition scanRegion = new RegionDefinition();
scanRegion.regionTop = 30;
scanRegion.regionBottom = 70;
scanRegion.regionRight = 15;
scanRegion.regionLeft = 85;
scanRegion.regionMeasuredByPercentage = 1;
try {
    mCameraEnhancer.setScanRegion(scanRegion);
} catch (CameraEnhancerException e) {
    e.printStackTrace();
}
```

The above settings can meet the majority of usage scenarios. However, if the performance is still not at a satisfactory level, the following articles can help you.

- [Optimizing Performance](quick-performance-settings.md)
- [UI Configuration](ui-configurations.md)

If you are facing license issues, the following page might help you.

- [Licence Activation]({{ site.license_activation }})
