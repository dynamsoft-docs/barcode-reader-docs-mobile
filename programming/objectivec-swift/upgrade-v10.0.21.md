---
layout: default-layout
title: How to Upgrade - Dynamsoft Barcode Reader for iOS
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK iOS edition from version 9.x to version 10.x with simple steps.
keywords: How to upgrade, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 8.0
---

# How to Upgrade

## From Version 9.x to 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcv_introduction }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes.

### Update the Libraries to 10.x Version

The Dynamsoft Barcode Reader SDK has been split into multiple libraries from the previous single library, and the dependency of the **xcframeworks** need to be updated.

* Local Dependency
    Add the following **xcframework** files into your project:

  * `DynamsoftCaptureVisionRouter.xcframework`
  * `DynamsoftBarcodeReader.xcframework`
  * `DynamsoftImageProcessing.xcframework`
  * `DynamsoftCore.xcframework`
  * `DynamsoftLicense.xcframework`
  * `DynamsoftCameraEnhancer.xcframework`(optional)

    ```groovy
    dependencies {
        implementation fileTree(include: ['*.aar'], dir: 'libs')   
    }
    ```

> Note: From DBR v10.0, **frameworks** are no longer provided in the SDK. Use **xcframeworks** instead.

* Remote Dependency(CocaPods)
  update **Podfile**:

    ```sh
    target 'HelloWorld' do
       use_frameworks!

    pod 'DynamsoftCaptureVisionRouter','{version-number}'
    pod 'DynamsoftBarcodeReader','{version-number}'
    pod 'DynamsoftCameraEnhancer','{version-number}'
    pod 'DynamsoftCore','{version-number}'
    pod 'DynamsoftLicense','{version-number}'
    pod 'DynamsoftImageProcessing','{version-number}'
    pod 'DynamsoftUtility','{version-number}'
    
    end
    ```

    >Note: Please view [user guide](user-guide.md#add-the-frameworks-via-cocoapods) for the correct version number.

### Update the License Activation Code

Starting from 10.0, we have unified the API for setting licenses across different Dynamsoft products.

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initLicense` | `DSLicenseManager.initLicense` |

* Code in 9.x:

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
> 
```objc
[DynamsoftBarcodeReader initLicense:@"YOUR-LICENSE-KEY" verificationDelegate:self];
- (void)DBRLicenseVerificationCallback:(bool)isSuccess error:(NSError *)error
{
  // Add your code for license verification.
}
```
>
```swift
DynamsoftBarcodeReader.initLicense("YOUR-LICENSE-KEY", verificationDelegate: self)
func dbrLicenseVerificationCallback(_ isSuccess: Bool, error: Error?)
{
  // Add your code for license verification.
}
```

* Code in 10.x:

<div class="sample-code-prefix template2"></div>
   >- Objective-C
   >- Swift
   >
> 
```objc
[DSLicenseManager initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
- (void)onLicenseVerified:(BOOL)isSuccess error:(nullable NSError *)error {
    if (!isSuccess && error != nil) {
        NSLog(@"error: %@", error);
    }
}
```
>
```swift
LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", verificationDelegate: self)
func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
   if !isSuccess {
          if let error = error {
             print("\(error.localizedDescription)")
          }
   }
}
```

### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | `DSCaptureVisionRouter.captureFromFile` |
| `BarcodeReader.decodeFileInMemory` | `DSCaptureVisionRouter.captureFromFileBytes` |
| `BarcodeReader.decodeBuffer` | `DSCaptureVisionRouter.captureFromBuffer` |
| `BarcodeReader.decodeBufferedImage` | `DSCaptureVisionRouter.captureFromImage` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

### Update Video Streaming Decoding APIs

The APIs for decoding video frames has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.setImageSource` | `DSCaptureVisionRouter.setInput` |
| `BarcodeReader.startScanning` | `DSCaptureVisionRouter.startCapturing` |
| `BarcodeReader.stopScanning` | `DSCaptureVisionRouter.stopCapturing` |
| `BarcodeReader.setTextResultListener` | `DSCaptureVisionRouter.addResultReceiver` |
| `BarcodeReader.setIntermediateResultListener` | `DSCaptureVisionRouter.IntermediateResultManager.addResultReceiver` |
| `BarcodeReader.set/getMinImageReadingInterval` | `SimplifiedCaptureVisionSettings.minImageCaptureInterval` |
| `BarcodeReader.enableResultVerification` | `DSMultiFrameResultCrossFilter.enableResultCrossVerification` |
| `BarcodeReader.enableDuplicateFilter` | `DSMultiFrameResultCrossFilter.enableResultDeduplication` |
| `Protocol ImageSource` | `Class DSImageSourceAdapter` |
| `Protocol TextResultListener` | `Protocol DSCapturedResultReceiver` |
| `Protocol IntermediateResultListener` | `Protocol DSIntermediateResultReceiver` |
| `class TextResult` | `class DSBarcodeResultItem` |

### Migrate Your Templates

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

The template-based APIs have been updated as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.initRuntimeSettingsWithFile` | `DSCaptureVisionRouter.initSettingsFromFile` |
| `BarcodeReader.initRuntimeSettingsWithString` | `DSCaptureVisionRouter.initSettings` |
| `BarcodeReader.outputSettingsToFile` | `DSCaptureVisionRouter.outputSettingsToFile` |
| `BarcodeReader.outputSettingsToString` | `DSCaptureVisionRouter.outputSettings` |
| `BarcodeReader.resetRuntimeSettings` | `DSCaptureVisionRouter.resetSettings` |
| `BarcodeReader.appendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.appendTplStringToRuntimeSettings` | **Not available**. |

### Migrate Your PublicRuntimeSettings

The class `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | `DSCaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `DSCaptureVisionRouter.updateSettings` |

#### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `DSSimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcv_parameters_reference }}target-roi-def/location.html?product=dbr&repoType=core) |
| `timeout` | [`timeout`]({{ site.dcv_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcv_parameters_reference }}capture-vision-template/timeout.html?product=dbr&repoType=core) |

#### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `DSSimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.android_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html?product=dbr&repoType=core) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.android_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcv_parameters_reference }}barcode-format-specification/min-result-confidence.html?product=dbr&repoType=core) |
| `localizationModes` | [`localizationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/localization-modes.html?product=dbr&repoType=core) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.android_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html?product=dbr&repoType=core) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core) |
| `deblurModes` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core) |
| `deblurLevel` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.android_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html?product=dbr&repoType=core) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-enhancement-modes.html?product=dbr&repoType=core) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcv_parameters_reference }}image-parameter/grayscale-transformation-modes.html?product=dbr&repoType=core) |
| `scaleDownThreshold` | [`scaleDownThreshold`]({{ site.android_api }}simplified-barcode-reader-settings.html#scaledownthreshold)| [`ImageParameter.ScaleDownThreshold`]({{ site.dcv_parameters_reference }}image-parameter/scale-down-threshold.html?product=dbr&repoType=core) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

#### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcv_parameters_reference }}image-parameter/binarization-modes.html?product=dbr&repoType=core) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html?product=dbr&repoType=core) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html?product=dbr&repoType=core) |
| `scaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcv_parameters_reference }}image-parameter/scale-up-modes.html?product=dbr&repoType=core) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcv_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html?product=dbr&repoType=core) |
| `terminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/terminate-setting.html?product=dbr&repoType=core) |

| PublicRuntimeSettings.furtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcv_parameters_reference }}image-parameter/colour-conversion-modes.html?product=dbr&repoType=core) |
| `regionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/region-predetection-modes.html?product=dbr&repoType=core) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcv_parameters_reference }}image-parameter/texture-detection-modes.html?product=dbr&repoType=core) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcv_parameters_reference }}image-parameter/text-detection-mode.html?product=dbr&repoType=core) & [`ImageParameter.IfEraseTextZone`]({{ site.dcv_parameters_reference }}image-parameter/if-erase-text-zone.html?product=dbr&repoType=core) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html?product=dbr&repoType=core) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html?product=dbr&repoType=core) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html?product=dbr&repoType=core) |
| `barcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html?product=dbr&repoType=core) |

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
