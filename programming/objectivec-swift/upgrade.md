---
layout: default-layout
title: How to Upgrade - Dynamsoft Barcode Reader for iOS
description: Follow the upgrade instructions to learn to upgrade Barcode Reader SDK iOS edition from version 9.x to version 10.x with simple steps.
keywords: How to upgrade, objective-c, oc, swift
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
pageStartVer: 8.0
permalink: /programming/objectivec-swift/upgrade.html
---

# How to Upgrade

## From Version 9.x to 10.x

Dynamsoft Barcode Reader SDK has been refactored to integrate with [`DynamsoftCaptureVision (DCV)`]({{ site.dcvb_introduction }}) architecture. To upgrade from version 9.x or earlier to 10.x, we recommend you to follow the [User Guide](foundational-guide.md) and re-write your codes.

### Update the Libraries

The Dynamsoft Barcode Reader SDK has been split into multiple libraries from the previous single library, and the dependency of the **xcframeworks** need to be updated.

#### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Up to Next Major Version`, then click **Add Package**.

4. Check all the **xcframeworks** and add.

#### Option 2: Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'ScanSingleBarcode' do
      use_frameworks!

   pod 'DynamsoftBarcodeReaderBundle','{version-number}'

   end
   ```

   >Note: Please view [user guide](user-guide.md#option-2-add-the-frameworks-via-cocoapods) for the correct version number.

2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

#### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, you will find a collection of **xcframework** files under the **Dynamsoft\Frameworks** directory.

   - 📄 **DynamsoftBarcodeReaderBundle.xcframework**
   - 📄 **DynamsoftCaptureVisionRouter.xcframework**
   - 📄 **DynamsoftCameraEnhancer.xcframework**
   - 📄 **DynamsoftBarcodeReader.xcframework**
   - 📄 **DynamsoftCore.xcframework**
   - 📄 **DynamsoftLicense.xcframework**
   - 📄 **DynamsoftImageProcessing.xcframework**
   - 📄 **DynamsoftUtility.xcframework**

2. Drag and drop the **xcframework** files into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

### Update the Template File

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

### Update your code

You have 2 Options when updating your code.

- [Update to New APIs with the foundational SDK](#option-1-update-to-new-apis-with-the-foundational-sdk)
- [Quick start a new project with BarcodeScanner Component](#option-2-quick-start-a-new-project-with-barcodescanner-component)

#### Option 1. Update to New APIs with the foundational SDK

##### Update the License Activation Code

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

##### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | `DSCaptureVisionRouter.captureFromFile` |
| `BarcodeReader.decodeFileInMemory` | `DSCaptureVisionRouter.captureFromFileBytes` |
| `BarcodeReader.decodeBuffer` | `DSCaptureVisionRouter.captureFromBuffer` |
| `BarcodeReader.decodeBufferedImage` | `DSCaptureVisionRouter.captureFromImage` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

##### Update Video Streaming Decoding APIs

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

##### Migrate Your Templates

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

##### Migrate Your PublicRuntimeSettings

The class `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | `DSCaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `DSCaptureVisionRouter.updateSettings` |

##### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `DSSimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html?product=dbr&repoType=core) |
| `timeout` | [`timeout`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html?product=dbr&repoType=core) |

##### Migrate to SimplifiedBarcodeReaderSettings

The following properties are replaced by similar properties under `DSSimplifiedBarcodeReaderSettings`. The majority of them can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `minBarcodeTextLength` | [`minBarcodeTextLength`]({{ site.android_api }}simplified-barcode-reader-settings.html#minbarcodetextlength) | [`BarcodeFormatSpecification.BarcodeTextLengthRangeArray`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-text-length-range-array.html?product=dbr&repoType=core) |
| `minResultConfidence` | [`minResultConfidence`]({{ site.android_api }}simplified-barcode-reader-settings.html#minresultconfidence) | [`BarcodeFormatSpecification.MinResultConfidence`]({{ site.dcvb_parameters_reference }}barcode-format-specification/min-result-confidence.html?product=dbr&repoType=core) |
| `localizationModes` | [`localizationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#localizationmodes) | [`BarcodeReaderTaskSetting.LocationModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/localization-modes.html?product=dbr&repoType=core) |
| `expectedBarcodesCount` | [`expectedBarcodesCount`]({{ site.android_api }}simplified-barcode-reader-settings.html#expectedbarcodescount) | [`BarcodeReaderTaskSetting.ExpectedBarcodesCount`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/expected-barcodes-count.html?product=dbr&repoType=core) |
| `barcodeFormatIds` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core) |
| `barcodeFormatIds_2` | [`barcodeFormatIds`]({{ site.android_api }}simplified-barcode-reader-settings.html#barcodeformatids) | [`BarcodeReaderTaskSetting.BarcodeFormatIds`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-format-ids.html?product=dbr&repoType=core) |
| `deblurModes` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core) |
| `deblurLevel` | [`deblurModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#deblurmodes) | [`BarcodeReaderTaskSetting.DeblurModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core) |
| `maxAlgorithmThreadCount` | [`maxThreadsInOneTask`]({{ site.android_api }}simplified-barcode-reader-settings.html#maxthreadsinonetask) | [`BarcodeReaderTaskSetting.MaxThreadsInOneTask`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/max-threads-in-one-task.html?product=dbr&repoType=core) |

> Remarks:
>
> * The 2 groups of barcode formats are merged.
> * `DeblurLevel` is deprecated. You can use `DeblurModes` instead.

| FurtherModes Property | SimplifiedBarcodeReaderSettings Property | Template File Parameter |
| ---------------------- | ----------------------------------------- | ----------------------- |
| `grayscaleTransformationModes` | [`grayscaleTransformationModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaletransformationmodes) | [`ImageParameter.GrayscaleTransformationModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-enhancement-modes.html?product=dbr&repoType=core) |
| `imagePreprocessingModes` | [`grayscaleEnhancementModes`]({{ site.android_api }}simplified-barcode-reader-settings.html#grayscaleenhancementmodes) | [`ImageParameter.GrayscaleEnhancementModes`]({{ site.dcvb_parameters_reference }}image-parameter/grayscale-transformation-modes.html?product=dbr&repoType=core) |
| `scaleDownThreshold` | [`scaleDownThreshold`]({{ site.android_api }}simplified-barcode-reader-settings.html#scaledownthreshold)| [`ImageParameter.ScaleDownThreshold`]({{ site.dcvb_parameters_reference }}image-parameter/scale-down-threshold.html?product=dbr&repoType=core) |

> Remarks: The mode `IPM_MORPHOLOGY` of `imagePreprocessingModes` is migrated to `BinarizationModes`. The mode arguments `MorphOperation`, `MorphOperationKernelSizeX`, `MorphOperationKernelSizeY`, `MorphShape` are now available for all modes of `BinarizationModes`.

##### Migrate to Template File

The following properties can only be set via a template file. Please [contact us](https://www.dynamsoft.com/company/customer-service/#contact){:target="_blank"} so that we can help you to transform your current settings to a new template file.

| PublicRuntimeSettings Property | Template File Parameter |
| ------------------------------- | ----------------------- |
| `binarizationModes` | [`ImageParameter.BinarizationModes`]({{ site.dcvb_parameters_reference }}image-parameter/binarization-modes.html?product=dbr&repoType=core) |
| `textResultOrderModes` | [`BarcodeReaderTaskSetting.TextResultOrderModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/text-result-order-modes.html?product=dbr&repoType=core) |
| `returnBarcodeZoneClarity` | [`BarcodeReaderTaskSetting.ReturnBarcodeZoneClarity`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/return-barcode-zone-clarity.html?product=dbr&repoType=core) |
| `scaleUpModes` | [`ImageParameter.ScaleUpModes`]({{ site.dcvb_parameters_reference }}image-parameter/scale-up-modes.html?product=dbr&repoType=core) |
| `barcodeZoneMinDistanceToImageBorders` | [`BarcodeFormatSpecification.BarcodeZoneMinDistanceToImageBorders`]({{ site.dcvb_parameters_reference }}barcode-format-specification/barcode-zone-min-distance-to-image-borders.html?product=dbr&repoType=core) |
| `terminatePhase` | [`BarcodeReaderTaskSetting.TerminateSettings`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/terminate-setting.html?product=dbr&repoType=core) |

| PublicRuntimeSettings.furtherModes Property | Template File Parameter |
| ---------------------- | ----------------------- |
| `colourConversionModes` | [`ImageParameter.ColourConversionModes`]({{ site.dcvb_parameters_reference }}image-parameter/colour-conversion-modes.html?product=dbr&repoType=core) |
| `regionPredetectionModes` | [`ImageParameter.RegionPredetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/region-predetection-modes.html?product=dbr&repoType=core) |
| `textureDetectionModes` | [`ImageParameter.TextureDetectionModes`]({{ site.dcvb_parameters_reference }}image-parameter/texture-detection-modes.html?product=dbr&repoType=core) |
| `textFilterModes` | [`ImageParameter.TextDetectionMode`]({{ site.dcvb_parameters_reference }}image-parameter/text-detection-mode.html?product=dbr&repoType=core) & [`ImageParameter.IfEraseTextZone`]({{ site.dcvb_parameters_reference }}image-parameter/if-erase-text-zone.html?product=dbr&repoType=core) |
| `dpmCodeReadingModes` | [`BarcodeReaderTaskSetting.DPMCodeReadingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/dpm-code-reading-modes.html?product=dbr&repoType=core) |
| `deformationResistingModes` | [`BarcodeReaderTaskSetting.DeformationResistingModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/deformation-resisting-modes.html?product=dbr&repoType=core) |
| `barcodeComplementModes` | [`BarcodeReaderTaskSetting.BarcodeComplementModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-complement-modes.html?product=dbr&repoType=core) |
| `barcodeColourModes` | [`BarcodeReaderTaskSetting.BarcodeColourModes`]({{ site.dcvb_parameters_reference }}barcode-reader-task-settings/barcode-colour-modes.html?product=dbr&repoType=core) |

##### Migrate to Other APIs

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSettings Property|
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

##### Removed

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `resultCoordinateType` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |

#### Option 2. Quick start a new project with BarcodeScanner Component

`BarcodeScanner` is a ready-to-use component that allows developers to quickly set up a barcode scanning app. With the built-in `BarcodeScannerViewController`, it streamlines the integration of barcode scanning functionality into any application.

- [View how to build your app with BarcodeScanner](user-guide.md).
