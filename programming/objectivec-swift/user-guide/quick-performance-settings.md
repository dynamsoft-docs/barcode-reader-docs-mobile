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
---

# Performance Optimization

By following the user guide, you have managed to create your own barcode reader application. However, you might still be having trouble in regards to some performance aspects:

* Some barcodes are not being recognized.
* Processing speed is too slow.
* Misread/inaccurate results.

In this article, we will share some solutions to help you solve the above issues.

## Decoding Unrecognized Barcodes

There are several reasons that may cause a barcode to be unrecognized.

* Failed to localize -
  * Small barcode in a relatively large image: optimize the `RegionPredetectionModes` setting. [Read more about how to use `RegionPredetectionModes`]({{ site.features }}use-region-predetection.html?lang=objc,swift)
  * The barcode is an inverted barcode: Enable `GTM_INVERTED` in the `GrayscaleTransformationModes`. [Read more about how to use `GrayscaleTransformationModes`]({{ site.features }}read-inverted-barcodes.html?lang=objc,swift)
  * Barcode is not localized for some other reason: Enable more `LocalizationModes`. [See details below](#enhance-barcode-localization)
* The barcode is located but the result cannot be decoded -
  * The barcode is blurry: Optimize the `DeblurModes` setting. [See details below](#process-blurry-barcode-zone)
  * The barcode module size is too small: Use `ScaleUpModes` or optimize the image source. [See details below](#read-small-scaled-barcode)
  * The barcode is incomplete: Use the `BarcodeComplementModes` parameter. [Read more about how to use `BarcodeComplementModes`]({{ site.features }}read-incomplete-barcodes.html?lang=objc,swift)
  * The barcode zone is deformed: Utilize the `DeformationResistingModes` parameter. [Read more about how to use `DeformationResistingModes`]({{ site.features }}read-deformed-barcodes.html?lang=objc,swift)

### Enhance Barcode Localization

`LocalizationModes` determines how the Barcode Reader localizes barcodes, which is the process of finding the barcode zone from an image or frame. If multiple localization modes are set, the library will go through each mode specified in `LocalizationModes` until the barcode count reaches the expected count or all the modes have been run. The available localization modes are:

* LM_CONNECTED_BLOCKS - recommended to always set this mode as the highest priority.
* LM_STATISTICS - optimized for QR Codes and Datamatrix.
* LM_LINES - optimized for 1D and PDF417 barcodes.
* LM_SCAN_DIRECTLY - best used in interactive video scenarios 
* LM_STATISTICS_MARKS - optimized for DPM codes. 
* LM_STATISTICS_POSTAL_CODE - optimized for Postal Codes.
* LM_CENTRE - optimized for localizing barcodes from the center of an image or frame.
* LM_ONED_FAST_SCAN - should be used if the setting calls for 1D barcodes to be read quickly.

`LocalizationModes` can be set via the `SimplifiedCaptureVisionSettings` or a template JSON file.

#### Update LocalizationModes via SimplifiedCaptureVisionSettings

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
NSError *error;
// Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
// Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
DSSimplifiedCaptureVisionSettings *captureVisionSettings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
captureVisionSettings.barcodeSettings.localizationModes = @[@(DSLocalizationModeConnectedBlocks),@(DSLocalizationModeStatistics),@(DSLocalizationModeLines)];
// Update the settings. Remember to specify the same template name you used when getting the settings.
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:captureVisionSettings error:&error];
```
>
```swift
do{
   // Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
   // Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
   let captureVisionSettings = try cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   captureVisionSettings.barcodeSettings?.localizationModes = [LocalizationMode.connectedBlocks.rawValue, LocalizationMode.statistics.rawValue, LocalizationMode.lines.rawValue]
   // Update the settings. Remember to specify the same template name you used when getting the settings.
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: captureVisionSettings)
}catch{
   // Add code to do when error occurs.
}
```

#### Update LocalizationModes via Template

Modify the `LocalizationModes` section of your template file and upload it with [`initSettingsFromFile`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html) method.

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

`DeblurModes` is the parameter that determines how to decode the localized barcode zone, which is the last stage of the barcode decoding algorithm. The more `DeblurModes` you enable, the higher the possibilty that the barcode zone is decoded although it could incur a higher time cost. The parameter can be set via both `SimplifiedCaptureVisionSettings` and the template file. The available `DeblurModes` are:

* DM_DIRECT_BINARIZATION
* DM_THRESHOLD_BINARIZATION
* DM_GRAY_EQUALIZATION
* DM_SMOOTHING
* DM_MORPHING
* DM_DEEP_ANALYSIS
* DM_SHARPENING
* DM_BASED_ON_LOC_BIN
* DM_SHARPENING_SMOOTHING

To learn all about the above modes, please visit this page.

#### Update DeblurModes via SimplifiedCaptureVisionSettings

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
NSError *error;
// Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
// Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
DSSimplifiedCaptureVisionSettings *captureVisionSettings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
captureVisionSettings.barcodeSettings.deblurModes = @[@(DSDeblurModeThresholdBinarization),@(DSDeblurModeDirectBinarization),@(DSDeblurModeGrayEqualization),@(DSDeblurModeDeepAnalysis)];
// Update the settings. Remember to specify the same template name you used when getting the settings.
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:captureVisionSettings error:&error];
```
>
```swift
do{
   // Obtain current runtime settings. `cvr` is an instance of `CaptureVisionRouter`.
   // Here we use `EnumPresetTemplate.PT_READ_BARCODES` as an example. You can change it to your own template name or the name of other preset template.
   let captureVisionSettings = try cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   captureVisionSettings.barcodeSettings?.deblurModes = [DeblurMode.thresholdBinarization.rawValue, DeblurMode.directBinarization.rawValue, DeblurMode.grayEqualization.rawValue, DeblurMode.deepAnalysis.rawValue]
   // Update the settings. Remember to specify the same template name you used when getting the settings.
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: captureVisionSettings)
}catch{
   // Add code to do when error occurs.
}
```

#### Update DeblurModes via Template

Modify the `DeblurModes` section of your template file and upload it with [`initSettingsFromFile`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#initsettingsfromfile) or [`initSettings`]({{ site.dcvb_ios_api }}capture-vision-router/settings.html#initsettings) method.

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

Generally, it is suggested to zoom-in using the camera to enlarge the module size of the barcode. If you are using `DynamsoftCameraEnhancer (DCE)` to setup the image source, you can use its zoom features to control the zoom-in/out of the camera. If the camera control is not available or you are going to decode from a still image, please read about [how to use the `ScaleUpMode`]({{ site.features }}read-barcodes-with-small-module-size.html?lang=objc,swift) to enlarge the barcode zone.

#### Enable the auto-zoom feature of DCE

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
[self.dce enableEnhancedFeatures:DSEnhancedFeaturesAutoZoom];
```
>
```swift
dce.enableEnhancedFeatures(EnhancedFeatures.autoZoom)
```

Use DCE to set the zoom factor:

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
[self.dce setZoomFactor:2.5];
```
>
```swift
dce.setZoomFactor(2.5)
```

## How to Improve the Speed

You use the following attempts to speed up the barcode decoding:

* Set a Region Of Interest (ROI). [Read more about how to setup ROI.]({{ site.features }}barcode-scan-region-mobile.html?lang=objc,swift).
* Scale down the image. [Read more about how to scale down the image.]({{ site.features }}barcode-scan-region-mobile.html?lang=objc,swift).
* Reduce the timeout. Configure the [barcodeSettings.timeout]({{ site.dbr_ios_api }}simplified-barcode-reader-settings.html) parameter of `SimplifiedCaptureVisionSettings` or update it via the template.
* Reduce the complexity of your barcode decoding template. For example reduce the `LocalizationModes` or the `DeblurModes`.

> How to use the `SimplifiedCaptureVisionSettings` and the template is introduced above in the [Enhance Barcode Localization](#enhance-barcode-localization) section. Please reference the above documents.

## How to Reduce the Possibility of Misread Results

* Implement result filter via `SimplifiedCaptureVisionSettings`.
  * `barcodeSettings.minResultConfidence` to filter out the low confidence results;
  * `barcodeSettings.minBarcodeTextLength` & `barcodeSettings.barcodeTextRegExPattern` to filter out unnecessary results;
* Implement multi-frame cross filter.

### How to Implement Multi-frame Cross Filter

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
>
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
[filter enableResultCrossVerification:DSCapturedResultItemTypeBarcode isEnabled:true];
[self.cvr addResultFilter:filter];
```
>
```swift
let filter = MultiFrameResultCrossFilter.init()
filter.enableResultCrossVerification(.barcode, isEnabled: true)
cvr.addResultFilter(filter)
```

## Further Improvements

Feel free to <a href="https://www.dynamsoft.com/contact/" target="_blank">contact us</a> for further improvements on the performance of your app. DBR has a lot of built-in parameters for image processing, localization, and barcode decoding. Please share the improvements that you are looking to make and our technical support team will help you configure the parameters to match your requirements.
