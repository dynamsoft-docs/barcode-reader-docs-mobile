---
layout: default-layout
title: Optimize Performance - Dynamsoft Barcode Reader Android Edition
description: This is the Optimize Performance page of Dynamsoft Barcode Reader for Android SDK.
keywords: Guide, Optimize Performance
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: false
---

# Quickly Adjust on the Performance

By following the previous guide, I believe you have managed to create your own barcode reader project. However, you might be still stuck in some aspects:

* There are some barcodes I can't recognize.
* The processing speed is too slow.
* There are misreading results.

In this article, we will share some solutions to help you solve the above issues.

## How to Decode the Unrecognized Barcodes

There are several reasons that may cause a barcode unrecognized.

* Failed to localize.
  * Small barcode in large image: Optimize the `RegionPredetectionModes` setting. [Read more about how to use `RegionPredetectionModes`]({{ site.features }}use-region-predetection.html?lang=android)
  * The barcode is an inverted barcode: Enable `GTM_INVERTED` of `GrayscaleTransformationModes`. [Read moreabout how to use `GrayscaleTransformationModes`]({{ site.features }}read-inverted-barcodes.html?lang=android)
  * Barcode is not localized for some other reason: Enable more `LocalizationModes`. [See details below](#enhance-barcode-localization)
* The barcode is located but the result cannot be decoded.
  * The barcode is blurry: Optimize the `DeblurModes` setting. [See details below](#process-blurry-barcode-zone)
  * The barcode module size is too small: Use `ScaleUpModes` or optimize the image source. [See details below](#read-small-scaled-barcode)
  * The barcode is incomplete: Enable `BarcodeComplementModes`. [Read more about how to use `BarcodeComplementModes`]({{ site.features }}read-incomplete-barcodes.html?lang=android)
  * The barcode zone is deformed: Enable `DeformationResistingModes`. [Read more about how to use `DeformationResistingModes`]({{ site.features }}read-deformed-barcodes.html?lang=android)

### Enhance Barcode Localization

`LocalizationModes` is the parameter that determines how the library find a barcode zone from the image. If set multiple modes for the parameter, the library will continue to try other `LocalizationModes` until the barcode count reaches the expected count, or all modes have been run. The candidate modes are available as follow:

* LM_CONNECTED_BLOCKS
* LM_STATISTICS
* LM_LINES
* LM_SCAN_DIRECTLY
* LM_STATISTICS_MARKS
* LM_STATISTICS_POSTAL_CODE
* LM_CENTRE
* LM_ONED_FAST_SCAN

The `LocalizationModes` is available for setting via either `SimplifiedCaptureVisionSettings` or the template file.

#### Update LocalizationModes via SimplifiedCaptureVisionSettings

```java
try {
   // Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
   // Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
   SimplifiedCaptureVisionSettings captureVisionSettings = cvr.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   captureVisionSettings.barcodeSettings.localizationModes = new int[]{EnumLocalizationModes.LM_CONNECTED_BLOCKS,EnumLocalizationModes.LM_STATISTICS,EnumLocalizationModes.LM_LINES};
   // Update the settings. Remember to specify the same template name you used when getting the settings.
   cvr.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, captureVisionSettings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

#### Update LocalizationModes via Template

Modify the `LocalizationModes` section of your template file and upload it with [`initSettingsFromFile`]({{ site.dcvb_android_api }}capture-vision-router/settings.html) method.

```json
{
   "LocalizationModes" :
   [
      {
         "Mode" : "LM_CONNECTED_BLOCKS"
      },
      {
         "Mode" : "LM_STATISTICS"
      },
      {
         "Mode" : "LM_LINES"
      }
   ]
}
```

### Process Blurry Barcode Zone

`DeblurModes` is the parameter that determines how to decode the localized barcode zone, which is the last stage of the barcode decoding algorithm. The more `DeblurModes` you enable, the higher possibilty the barcode zone is decoded. The parameter is available for setting via both `SimplifiedCaptureVisionSettings` and the template file.

#### Update DeblurModes via SimplifiedCaptureVisionSettings

```java
try {
   // Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
   // Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
   SimplifiedCaptureVisionSettings captureVisionSettings = cvr.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   captureVisionSettings.barcodeSettings.deblurModes = new int[]{EnumDeblurMode.DM_THRESHOLD_BINARIZATION,EnumDeblurMode.DM_DIRECT_BINARIZATION,EnumDeblurMode.DM_GRAY_EQUALIZATION,EnumDeblurMode.DM_DEEP_ANALYSIS};
   // Update the settings. Remember to specify the same template name you used when getting the settings.
   cvr.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, captureVisionSettings);
} catch (CaptureVisionRouterException e) {
   e.printStackTrace();
}
```

#### Update DeblurModes via Template

Modify the `DeblurModes` section of your template file and upload it with [`initSettingsFromFile`]({{ site.dcvb_android_api }}capture-vision-router/settings.html#initsettingsfromfile) or [`initSettings`]({{ site.dcvb_android_api }}capture-vision-router/settings.html#initsettings) method.

```json
{
    "DeblurModes":
    [
        {
            "Mode": "DM_BASED_ON_LOC_BIN"
        },
        {
            "Mode": "DM_THRESHOLD_BINARIZATION" 
        },
        {
            "Mode": "DM_DIRECT_BINARIZATION" 
        },
        {
            "Mode": "DM_GRAY_EQUALIZATION" 
        },
        {
            "Mode": "DM_DEEP_ANALYSIS" 
        }
    ]
}
```

### Read Small Scaled Barcode

Generally, it is suggested to zoom-in the camera to enlarge the module size of the barcode. If you are using `DynamsoftCameraEnhancer (DCE)` to setup the image source, you can use its zoom features to control the zoom-in/out of the camera. If the camera control is not available for use device or you are going to decode from a still image, please read about [how to use the `ScaleUpMode`]({{ site.features }}read-barcodes-with-small-module-size.html?lang=android) to enlarge the barcode zone.

Enable the auto-zoom feature of DCE:

```java
try {
   dce.enableEnhancedFeatures(EnumEnhancerFeatures.EF_AUTO_ZOOM);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

Use DCE to set the zoom factor:

```java
try {
   dce.setZoomFactor(2.5f);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

## How to Improve the Speed

You use the following attempts to speed up the barcode decoding:

* Set a Region Of Interest (ROI). [Read more about how to setup ROI.]({{ site.features }}barcode-scan-region-mobile.html?lang=android).
* Scale down the image. [Read more about how to scale down the image.]({{ site.features }}barcode-scan-region-mobile.html?lang=android).
* Reduce the timeout. Configure the [barcodeSettings.timeout]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html) parameter of `SimplifiedCaptureVisionSettings` or update it via the template.
* Reduce the complexity of your barcode decoding template. For example reduce the `LocalizationModes` or the `DeblurModes`.

> How to use the `SimplifiedCaptureVisionSettings` and the template is introduced above in the [Enhance Barcode Localization](#enhance-barcode-localization) section. Please reference the above documents.

## How to Reduce the Misreading Results

* Implement result filter via `SimplifiedCaptureVisionSettings`.
  * `barcodeSettings.minResultConfidence` to filter out the low confidence results;
  * `barcodeSettings.minBarcodeTextLength` & `barcodeSettings.barcodeTextRegExPattern` to filter out unnecessary results;
* Implement multi-frame cross filter.

### How to Implement Multi-frame Cross Filter

```java
MultiFrameResultCrossFilter filter =  new MultiFrameResultCrossFilter();
filter.enableResultCrossVerification(EnumCapturedResultItemType.CRIT_BARCODE,true);
cvr.addResultFilter(filter);
```

## Further Improvements

Feel free to <a href="https://www.dynamsoft.com/contact/" target="_blank">contact us</a> for further improvements on your performance . DBR has a lot of built-in parameters for image processing, localization supporting and barcode decoding. Please feedback your problems to us so that our technical support team will help you configure the parameters to match your requirements.
