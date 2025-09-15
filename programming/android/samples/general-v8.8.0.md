---
layout: default-layout
title: General Settings Sample - Dynamsoft Barcode Reader for Android
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/android/samples/general-v8.8.0.html
---

# GeneralSettings Sample

This sample shows how to configure general barcode settings like the barcode formats, expected barcode count and the scan region when using Dynamsoft Barcode Reader Android SDK.

**View Samples (on GitHub)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v8.8.0/android/GeneralSettings/" target="_blank">Java (Android) General Settings Sample (v8.8.0)</a>

## Configure the Settings via PublicRuntimeSettings

### Specify Barcode Format and Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app. These parameters are all available for users to make changes through the class [`PublicRuntimeSettings`]({{ site.android_api }}auxiliary-PublicRuntimeSettings.html). To view all available barcode formats, please view the enumeration [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android) and [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android).

**Code Snippet**

```java
// General settings (including barcode format, barcode count and scan region) for the instance.
// Obtain current runtime settings of instance.
PublicRuntimeSettings runtimeSettings = reader.getRuntimeSettings();
// Set the expected barcode format you want to read.
// The barcode format our library will search for is composed of BarcodeFormat group 1 and BarcodeFormat group 2.
// So you need to specify the barcode format in group 1 and group 2 individually.
runtimeSettings.barcodeFormatIds = EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_PDF417 | EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_DATAMATRIX |EnumBarcodeFormat.BF_AZTEC;
runtimeSettings.barcodeFormatIds_2 = 0;
// Set the expected barcode count you want to read.
runtimeSettings.expectedBarcodesCount = 5;
// Apply the new settings to the instance
reader.updateRuntimeSettings(runtimeSettings);
```

**Related APIs**

- Class [`PublicRuntimeSettings`]({{ site.android_api }}auxiliary-PublicRuntimeSettings.html?lang=android)
- Enum [`BarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=android)
- Enum [`BarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=android)

### Specify the Scan Region

The scan region information is stored in [`RegionDefinition`]({{ site.android_api }}auxiliary-RegionDefinition.html) class. To set the scan region, you can make the region settings in class [`RegionDefinition`]({{ site.android_api }}auxiliary-RegionDefinition.html) and upload the settings through the class [`PublicRuntimeSettings`]({{ site.android_api }}auxiliary-PublicRuntimeSettings.html).

Please note, when using your phone in **portrait mode** the orientation of the mobile frame is rotated 90 degrees counterclockwise from the orientation of your device. The following image illustrates the mobile frames' orientation based on the camera view, either portrait or landscape.

<div align="center">
    <p><img src="../../assets/image-orientation.png" width="70%" alt="region"></p>
    <p>How to Configure the Scan Region</p>
</div>

The **regionTop**, **regionBottom**, **regionLeft** and **regionRight** parameters in the class [`RegionDefinition`]({{ site.android_api }}auxiliary-RegionDefinition.html) stand for the region of the **frame** not the camera view. Since the parameters are based on the frame view instead of the camera view, let's see how the parameters would look like in the camera view once we rotate the frame view 90 degrees clockwise. This is what we get based on the last example:

<div align="center">
    <p><img src="../../assets/frame-and-camera-view.png" width="70%" alt="orientation"></p>
    <p>Frame View vs Camera View</p>
</div>

Therefore, please make sure that you are setting the correct parameters for the border of your scan region. Let's say that you are looking to create a scan region on mobile with the following values
```
regionTop = 30%
regionBottom = 70%
regionLeft = 15%
regionRight = 85%
```
Now let's do the same transformation of the frame view to the camera view as we did in the example above, considering again that the region parameters based on the frame view have to be rotated 90 degrees clockwise to get the camera view. The visual is then followed by the corresponding code snippet

<div align="center">
    <p><img src="../../assets/config-scan-region.png" width="70%" alt="region-orientation"></p>
    <p>Region Orientation</p>
</div>

**Code Snippet**

```java
// General settings (including barcode format, barcode count and scan region) for the instance.
// Obtain current runtime settings of instance.
PublicRuntimeSettings runtimeSettings = reader.getRuntimeSettings();
RegionDefinition regionDefinition = new RegionDefinition();
// Set the ROI(region of insterest) to speed up the barcode reading process.
// Note: DBR supports setting coordinates by pixels or percentages. The origin of the coordinate system is the upper left corner point.
// The int value 15 means the top of the scan region margins 15% from the top of screen.
regionDefinition.regionTop = 15;
regionDefinition.regionBottom = 85;
regionDefinition.regionLeft = 30;
regionDefinition.regionRight = 70;
regionDefinition.regionMeasuredByPercentage = 1;
runtimeSettings.region = regionDefinition;
// Apply the new settings to the instance
reader.updateRuntimeSettings(runtimeSettings);
```

**Related APIs**

- Class [`RegionDefinition`]({{ site.android_api }}auxiliary-RegionDefinition.html)
- Class [`PublicRuntimeSettings`]({{ site.android_api }}auxiliary-PublicRuntimeSettings.html)

## Configure the Settings via JSON Template

Besides using the [`PublicRuntimeSettings`]({{ site.android_api }}auxiliary-PublicRuntimeSettings.html) class, you can also upload the general barcode settings from stringified JSON data or a JSON file.

### Update the Runtime Settings via JSON String

Use method [`initRuntimeSettingsWithString`]({{ site.android_api }}primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithstring) to upload the settings via a JSON string.

**Code Snippet**

```java
reader.initRuntimeSettingsWithString("{\"Version\":\"3.0\", \"ImageParameter\":{\"Name\":\"IP1\", \"BarcodeFormatIds\":[\"BF_QR_CODE\"], \"ExpectedBarcodesCount\":10}}", EnumConflictMode.CM_OVERWRITE);
```

### Update the Runtime Settings via JSON File

Use method [`initRuntimeSettingsWithFile`]({{ site.android_api }}primary-parameter-and-runtime-settings-advanced.html#initruntimesettingswithfile) to upload the settings via a JSON file.

**Code Snippet**

```java
// Overwrite the settings if the settings already exist.
reader.initRuntimeSettingsWithFile("your template file path", EnumConflictMode.CM_OVERWRITE);
```
