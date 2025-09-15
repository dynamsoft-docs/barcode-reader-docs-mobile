---
layout: default-layout
title: Optimize Performance - Dynamsoft Barcode Reader for Android
description: This is the Optimize Performance page of Dynamsoft Barcode Reader for Android SDK.
keywords: Guide, Android, Optimize Performance
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
permalink: /programming/android/quick-performance-settings-v9.6.20.html
---

# Optimizing Performance

By following the previous guide, you managed to create your own barcode reader project. However, you might look to improve the performance of the reader in some areas:

- Unrecognized barcodes.
- Slow processing speed.
- Misread results.

In this article, we will share some solutions to help you solve the above issues.

## How to Decode Unrecognized Barcodes

There are several reasons that may cause a barcode to be unrecognized. 

Generally speaking

- The barcode reader failed to locate the barcode.
- The barcode is located but the result cannot be decoded.

**Adjust the DeblurLevel**

`DeblurLevel` is the parameter that controls how much effort the library spends on decoding the localized barcodes. Setting a higher value for `DeblurLevel` will improve the recognition rate and decrease the recognition speed at the same time. `DeblurLevel` is set to 9 (the highest level) by default. Therefore, if you find the recognition speed is not satisfying, you can reduce the `DeblurLevel` to balance the performance.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,9] | 9 |

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.deblurLevel = 9;
reader.updateRuntimeSettings(settings);
```

**Enlarge the resolution**

When decoding from the video streaming, it is recommended to set the resolution to 1080P.

```java
// You can use the following method to change the resolution.
cameraEnhancer.setResolution(EnumResolution.RESOLUTION_1080P);
```

**Add Localization Modes**

The `LocalizationModes` determines how the library locates the barcode. Using multiple `LocalizationModes` can help the library to find at least one barcode for further processing. When you find there are barcodes that can't be recognized, you may try adding extra parameters to the `LocalizationModes`.

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();
// You can specify at most 8 localization modes.
// The localization modes will be executed in the order in which they are set.
// If the barcode reader decode enough barcodes via a forward mode, the behind modes will not be executed
// Always put LM_SCAN_DIRECTLY before LM_CONNECTED_BLOCKS and put LM_LINES before LM_STATISTICS. Otherwise, they can't improve the readability.
settings.localizationModes = new int[]{EnumLocalizationMode.LM_SCAN_DIRECTLY,EnumLocalizationMode.LM_CONNECTED_BLOCKS,EnumLocalizationMode.LM_LINES,EnumLocalizationMode.LM_STATISTICS};
reader.updateRuntimeSettings(settings);
```

## How to Improve the Speed

**Set ScaleDownThreshold**

Images with higher pixel density than the threshold will be scaled down. The default value of `ScaleDownThreshold` is 2300 (pixel). You can set a smaller value when you need to speed up the recognition.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [512,0x7fffffff] | 2300 |

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.scaleDownThreshold = 1200;
reader.updateRuntimeSettings(settings);
```

**Reduce Timeout for Video Streaming Barcode Decoding**

`Timeout`, which is measured in milliseconds, determines the maximum time the library will spend on each image. Decreasing the value of `Timeout` might help you on improving the recognition speed of video decoding. Some low-end devices may not be able to complete the barcode processing if the `Timeout` is too short. Make sure to test that you are using a suitable `Timeout` value for low end devices.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,0x7fffffff] | 10000 |

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.timeout = 9;
reader.updateRuntimeSettings(settings);
```

## How to Filter out Misread Results

**Increase the Confidence Level**

`MinResultConfidence` is the parameter that controls the result confidence to filter the results below the set confidence. The default value of `MinResultConfidence` is 30. You can set `MinResultConfidence` higher to get even more accurate results.

| Value Type | Value Range | Default Value |
| ---------- | ----------- | ------------- |
| int | [0,100] | 30 |

```java
PublicRuntimeSettings settings = reader.getRuntimeSettings();
settings.minResultConfidence = 40;
reader.updateRuntimeSettings(settings);
```

**Enable Result Verification**

Use multiple barcode results from different video frames to verify the correctness of the results. You can enable the result verification to further improve the result accuracy.

```java
reader.enableResultVerification(true);
```

## Other Settings

If the above settings can not solve the issues you have, feel free to <a href="https://www.dynamsoft.com/contact/" target="_blank">contact us</a> for further technical support. DBR has a lot of built-in parameters for image processing, localization supporting and barcode decoding. Please feedback your problems to us so that our technical support team will help you configure the parameters to match your requirements.
