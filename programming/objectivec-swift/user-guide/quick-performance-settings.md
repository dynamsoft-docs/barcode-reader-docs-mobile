---
layout: default-layout
title: Optimize Performance - Dynamsoft Barcode Reader for iOS
description: This is the Optimize Performance page of Dynamsoft Barcode Reader for iOS SDK.
keywords: Guide, Optimize Performance
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: false
permalink: /programming/objectivec-swift/quick-performance-settings.html
---

# Quickly Adjust on the Performance

By following the previous guide, I believe you have managed to create your own barcode reader project. However, you might be still stuck in some aspects:

* There are some barcodes I can't recognize.
* The processing speed is too slow.
* There are misreading results.

In this article, we will share some solutions to help you solve the above issues.

## How to Decode the Unrecognized Barcodes

There are several reasons that may cause a barcode unrecognized.

Generally speaking

* The barcode reader failed to locate the barcode.
* The barcode is located but the result cannot be decoded.

**Enable More DeblurModes**

DeblurMode is the parameter that determines how to decode the localized barcode zone.

* DM_BASED_ON_LOC_BIN
* DM_DIRECT_BINARIZATION
* DM_THRESHOLD_BINARIZATION
* DM_GRAY_EQUALIZATION
* DM_SMOOTHING
* DM_MORPHING
* DM_DEEP_ANALYSIS
* DM_SHARPENING
* DM_SHARPENING_SMOOTHING

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,9] | 9 |

```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.deblurLevel = 0
   try barcodeReader.updateRuntimeSettings(settings!)
}catch{
   // Add your code to deal with exceptions
}
```

**Enlarge the Resolution**

When decoding from the video streaming, it is recommended to set the resolution to 1080P.

```swift
dce.setResolution(Resolution.EnumRESOLUTION_1080P)
```

**Add Localization Modes**

The `LocalizationModes` determines how the library locates the barcode. Set multiple `LocalizationModes` can help the library to find at least one barcode for further processing. When you find there are barcodes that can't be recognized, you may try adding extra parameters to the `LocalizationModes`.

```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.localizationModes = [EnumLocalizationMode.scanDirectly, EnumLocalizationMode.connectedBlocks]
   try barcodeReader.updateRuntimeSettings(settings!)
}catch{
   // Add your code to deal with exceptions
}
```

## How to Improve the Speed

**Set ScaleDownThreshold**

Images with higher pixel density than the threshold will be scaled down. The default value of `ScaleDownThreshold` is 2300 (pixel). You can set a smaller value when you need to speed up the recognition.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [512,0x7fffffff] | 2300 |

```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.scaleDownThreshold = 1200
   try barcodeReader.updateRuntimeSettings(settings!)
}catch{
   // Add your code to deal with exceptions
}
```

**Reduce Timeout for Video Streaming Barcode Decoding**

`Timeout`, which is measured by milliseconds, determines the maximum time the library will spend on each image. Decreasing the value of `Timeout` might help you on improving the recognition speed of video decoding. Some low-end devices may not be able to complete the barcode processing if the `Timeout` is too short. Ensure to fully test before given a suitable `Timeout` for low-end devices.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,0x7fffffff] | 10000 |

```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.timeout = 500
   try barcodeReader.updateRuntimeSettings(settings!)
}catch{
   // Add your code to deal with exceptions
}
```

## How to Filter out the Misreading Results

**Increase Confidence Level**

`MinResultConfidence` is the parameter that controls the result confidence to filter the results below the set confidence. The default value of `MinResultConfidence` is 30. You can set `MinResultConfidence` higher to get even more accurate results.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,100] | 30 |

```swift
do{
   let settings = try barcodeReader.getRuntimeSettings()
   settings.minResultConfidence = 50
   try barcodeReader.updateRuntimeSettings(settings!)
}catch{
   // Add your code to deal with exceptions
}
```

**Enable Result Verification**

Use multiple barcode results from different video frames to verify the correctness of the results. You can enable the result verification to further improve the result accuracy.

```swift
reader.enableResultVerification = true
```

## Other Settings

If the above settings can not solve the issues you have, feel free to <a href="https://www.dynamsoft.com/company/contact/" target="_blank">contact us</a> for further technical support. DBR has a lot of built-in parameters for image processing, localization supporting and barcode decoding. Please feedback your problems to us so that our technical support team will help you configure the parameters to match your requirements.
