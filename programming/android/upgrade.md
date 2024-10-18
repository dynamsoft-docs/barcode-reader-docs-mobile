---
layout: default-layout
title: How to update - Dynamsoft Barcode Reader for Android
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK Android edition from version 7.x & 8.0 to version 8.x with simple steps.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 10.0
permalink: /programming/android/upgrade.html
---

# How to Upgrade

## From Version 9.x to 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_introduction }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes.

### Update the Libraries to 10.x Version

The Dynamsoft Barcode Reader SDK has been split into multiple libraries from the previous single library, and the dependency configuration in the `app\build.gradle` file needs to be updated accordingly.

- Local Dependency
    Put the following `aar` files into `libs` directory and update `app\build.gradle` file:

  - `DynamsoftCaptureVisionRouter.aar`
  - `DynamsoftBarcodeReader.aar`
  - `DynamsoftImageProcessing.aar`
  - `DynamsoftCore.aar`
  - `DynamsoftLicense.aar`
  - `DynamsoftCameraEnhancer.aar`(optional)

    ```groovy
    dependencies {
        implementation fileTree(include: ['*.aar'], dir: 'libs')   
    }
    ```

- Remote Dependency(Maven)
  update `app\build.gradle` file:

    ```groovy
    dependencies {
        implementation 'com.dynamsoft:dynamsoftbarcodereaderdundle:{version-number}'
    }
    ```

    >Note: Please view [user guide](user-guide.md#add-the-libraries-via-maven) for the correct version number.

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initLicense` | `LicenseManager.initLicense` |

- Java code in 9.x:

```java
BarcodeReader.initLicense("Put your license", new DBRLicenseVerificationListener() {
    @Override
    public void DBRLicenseVerificationCallback(boolean isSuccess, Exception error) {
        if(!isSuccess){
            error.printStackTrace();
        }
    }
});
```

- Java code in 10.x:

```java
LicenseManager.initLicense("Put your license", this, new LicenseVerificationListener() {
    @Override
    public void onLicenseVerified(boolean isSuccess, Exception error) {
        if(!isSuccess){
            error.printStackTrace();
        }
    }
});
```

### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | `CaptureVisionRouter.capture(String filePath, String templateName)` |
| `BarcodeReader.decodeFileInMemory` | `CaptureVisionRouter.capture(byte[] fileBytes, String templateName)` |
| `BarcodeReader.decodeBuffer` | `CaptureVisionRouter.capture(ImageData imageData, String templateName)` |
| `BarcodeReader.decodeBufferedImage` | `CaptureVisionRouter.capture(Bitmap bitmap, String templateName)` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

### Update Video Streaming Decoding APIs

The APIs for decoding video frames has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.setImageSource` | `CaptureVisionRouter.setInput` |
| `BarcodeReader.startScanning` | `CaptureVisionRouter.startCapturing` |
| `BarcodeReader.stopScanning` | `CaptureVisionRouter.stopCapturing` |
| `BarcodeReader.setTextResultListener` | `CaptureVisionRouter.addResultReceiver` |
| `BarcodeReader.setIntermediateResultListener` | `CaptureVisionRouter.IntermediateResultManager.addResultReceiver` |
| `BarcodeReader.set/getMinImageReadingInterval` | `SimplifiedCaptureVisionSettings.minImageCaptureInterval` |
| `BarcodeReader.enableResultVerification` | `MultiFrameResultCrossFilter.enableResultCrossVerification` |
| `BarcodeReader.enableDuplicateFilter` | `MultiFrameResultCrossFilter.enableResultDeduplication` |
| `interface ImageSource` | `interface ImageSourceAdapter` |
| `interface TextResultListener` | `interface CapturedResultReceiver` |
| `interface IntermediateResultListener` | `interface IntermediateResultReceiver` |
| `class TextResult` | `class BarcodeResultItem` |

### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initRuntimeSettingsWithFile` | `CaptureVisionRouter.initSettingsFromFile` |
| `BarcodeReader.initRuntimeSettingsWithString` | `CaptureVisionRouter.initSettings` |
| `BarcodeReader.outputSettingsToFile` | `CaptureVisionRouter.outputSettingsToFile` |
| `BarcodeReader.outputSettingsToString` | `CaptureVisionRouter.outputSettings` |
| `BarcodeReader.resetRuntimeSettings` | `CaptureVisionRouter.resetSettings` |
| `BarcodeReader.appendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.appendTplStringToRuntimeSettings` | **Not available**. |

### Migrate Your PublicRuntimeSettings

The class `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | `CaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `CaptureVisionRouter.updateSettings` |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html?product=dbr) |
| `timeout` | [`timeout`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html?product=dbr) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `SimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.android_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html?product=dbr) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.android_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html?product=dbr) |
| `localizationModes` | [`localizationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html?product=dbr) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.android_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html?product=dbr) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr) |
| `deblurModes` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr) |
| `deblurLevel` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.android_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html?product=dbr) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html?product=dbr) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html?product=dbr) |
| `scaleDownThreshold` | [`scaleDownThreshold`]({{ site.android_api }}simplified-barcode-reader-settings.html#scaledownthreshold)| [`ImageParameter.ScaleDownThreshold`]({{ site.dcvb_parameters_reference }}image-parameter/scale-down-threshold.html?product=dbr) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html?product=dbr) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html?product=dbr) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html?product=dbr) |
| `scaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcvb_parameters_reference }}image-parameter/scale-up-modes.html?product=dbr) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html?product=dbr) |
| `terminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/terminate-setting.html?product=dbr) |

| PublicRuntimeSettings.furtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html?product=dbr) |
| `regionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html?product=dbr) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html?product=dbr) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html?product=dbr) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html?product=dbr) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html?product=dbr) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html?product=dbr) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html?product=dbr) |
| `barcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html?product=dbr) |

#### Migrate to Other APIs

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSettings Property|
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

#### Removed

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `resultCoordinateType` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
