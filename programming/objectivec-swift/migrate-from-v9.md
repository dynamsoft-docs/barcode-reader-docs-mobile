---
layout: default-layout
title: Migrate from v9 to v11 - Dynamsoft Barcode Reader for iOS
description: Follow this page to learn to upgrade Barcode Reader SDK iOS edition from v9 to v11.
keywords: updates guide, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Migrate from v9 to v11

> [!IMPORTANT]
> **We strongly recommend upgrading to v11.x.** All future algorithm improvements, performance optimizations, and new features will be developed exclusively for v11 and later versions.
> **Critical: Version 9.x and earlier are on a legacy architecture.** All new algorithm development, performance improvements, and features are built exclusively on the DynamsoftCaptureVision (DCV) architecture introduced in v10+. 
> 
> **Staying on v9.x or earlier means:**
> - ❌ No access to new barcode recognition algorithms
> - ❌ No future performance optimizations
> - ❌ Missing out on new symbology support
> - ❌ Limited to critical security patches only
>
> **Upgrading to v11 provides:**
> - ✅ Access to all future algorithm enhancements
> - ✅ Continuous performance improvements
> - ✅ New features and capabilities as they're released
> - ✅ Full technical support and active maintenance

Dynamsoft Barcode Reader SDK has been refactored to integrate with DynamsoftCaptureVision (DCV) architecture since version 10. To upgrade from version 9.x or earlier to 11.x, we recommend you to follow the [User Guide](user-guide.md) and re-write your codes. This section highlights only the key changes and necessary actions for upgrading the SDK.

**⚠️ Version 9.x is in maintenance mode only** - no new features or algorithm updates will be backported.

## Update the Libraries

There are three ways in which you can include the `DynamsoftBarcodeReaderBundle` library in your app:

### Option 1: Add the xcframeworks via Swift Package Manager

1. In your Xcode project, go to **File --> AddPackages**.

2. In the top-right section of the window, search "https://github.com/Dynamsoft/barcode-reader-spm"

3. Select `barcode-reader-spm`, choose `Up to Next Major Version`, then click **Add Package**.

4. Check all the **xcframeworks** and add.

### Option 2: Add the Frameworks via CocoaPods

1. Add the frameworks in your **Podfile**, replace `TargetName` with your real target name.

   ```sh
   target 'ScanSingleBarcode' do
      use_frameworks!

   pod 'DynamsoftBarcodeReaderBundle','{version-number}'

   end
   ```

   <div class="blockquote-note"></div>
   > Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.


2. Execute the pod command to install the frameworks and generate workspace(**[TargetName].xcworkspace**):

   ```sh
   pod install
   ```

### Option 3: Add Local xcframeworks files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, you will find a collection of **xcframework** files under the **Dynamsoft\Frameworks** directory.

   - 📄 **DynamsoftBarcodeReaderBundle.xcframework**
   - 📄 **DynamsoftCaptureVisionBundle.xcframework**

2. Drag and drop the above **.xcframework** files into your Xcode project. Make sure to check `Copy items if needed` and `Create groups` to copy the framework into your project's folder.

3. Click on the project settings then go to **General –> Frameworks, Libraries, and Embedded Content**. Set the **Embed** field to **Embed & Sign** for all above **xcframeworks**.

### Update the Template File

If you are using a template file, please use the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/) to convert it to the latest version. 

### API Change Reference List

License activation:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.initLicense` | `DSLicenseManager.initLicense` |

Process Single Image:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.decodeFile` | `DSCaptureVisionRouter.captureFromFile` |
| `BarcodeReader.decodeFileInMemory` | `DSCaptureVisionRouter.captureFromFileBytes` |
| `BarcodeReader.decodeBuffer` | `DSCaptureVisionRouter.captureFromBuffer` |
| `BarcodeReader.decodeBufferedImage` | `DSCaptureVisionRouter.captureFromImage` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

Process the video streaming:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.setImageSource` | `DSCaptureVisionRouter.setInput` |
| `BarcodeReader.startScanning` | `DSCaptureVisionRouter.startCapturing` |
| `BarcodeReader.stopScanning` | `DSCaptureVisionRouter.stopCapturing` |
| `BarcodeReader.setTextResultListener` | `DSCaptureVisionRouter.addResultReceiver` |
| `BarcodeReader.setIntermediateResultListener` | `DSCaptureVisionRouter.IntermediateResultManager.addResultReceiver` |
| `BarcodeReader.set/getMinImageReadingInterval` | `DSSimplifiedCaptureVisionSettings.minImageCaptureInterval` |
| `BarcodeReader.enableResultVerification` | `DSMultiFrameResultCrossFilter.enableResultCrossVerification` |
| `BarcodeReader.enableDuplicateFilter` | `DSMultiFrameResultCrossFilter.enableResultDeduplication` |
| `Protocol ImageSource` | `Class DSImageSourceAdapter` |
| `Protocol TextResultListener` | `Protocol DSCapturedResultReceiver` |
| `Protocol IntermediateResultListener` | `Protocol DSIntermediateResultReceiver` |
| `class TextResult` | `class DSBarcodeResultItem` |

Template and Settings Management:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.initRuntimeSettingsWithFile` | `DSCaptureVisionRouter.initSettingsFromFile` |
| `BarcodeReader.initRuntimeSettingsWithString` | `DSCaptureVisionRouter.initSettings` |
| `BarcodeReader.outputSettingsToFile` | `DSCaptureVisionRouter.outputSettingsToFile` |
| `BarcodeReader.outputSettingsToString` | `DSCaptureVisionRouter.outputSettings` |
| `BarcodeReader.resetRuntimeSettings` | `DSCaptureVisionRouter.resetSettings` |
| `BarcodeReader.appendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.appendTplStringToRuntimeSettings` | **Not available**. |
| `BarcodeReader.getRuntimeSettings` | `DSCaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `DSCaptureVisionRouter.updateSettings` |
| `PublicRuntimeSettings.region` | `DSSimplifiedCaptureVisionSettings.roi` & `DSSimplifiedCaptureVisionSettings.roiMeasuredInPercentage` |
| `PublicRuntimeSettings.timeout` | `DSSimplifiedCaptureVisionSettings.timeout` |
| `PublicRuntimeSettings.minBarcodeTextLength` | `DSSimplifiedBarcodeReaderSettings.minBarcodeTextLength` |
| `PublicRuntimeSettings.minResultConfidence` | `DSSimplifiedBarcodeReaderSettings.minResultConfidence` |
| `PublicRuntimeSettings.localizationModes` | `DSSimplifiedBarcodeReaderSettings.localizationModes` |
| `PublicRuntimeSettings.expectedBarcodesCount` | `DSSimplifiedBarcodeReaderSettings.expectedBarcodesCount` |
| `PublicRuntimeSettings.barcodeFormatIds` | `DSSimplifiedBarcodeReaderSettings.barcodeFormatIds` |
| `PublicRuntimeSettings.barcodeFormatIds_2` | `DSSimplifiedBarcodeReaderSettings.barcodeFormatIds` |
| `PublicRuntimeSettings.deblurModes` | `DSSimplifiedBarcodeReaderSettings.deblurModes` |
| `PublicRuntimeSettings.deblurLevel` | **Not available**, use `DSSimplifiedBarcodeReaderSettings.deblurLevel`. |
| `PublicRuntimeSettings.maxAlgorithmThreadCount` | `DSSimplifiedBarcodeReaderSettings.maxThreadsInOneTask` |
| `FurtherModes.grayscaleTransformationModes` | `DSSimplifiedBarcodeReaderSettings.grayscaleTransformationModes` |
| `FurtherModes.imagePreprocessingModes` | `DSSimplifiedBarcodeReaderSettings.grayscaleEnhancementModes` |
| `FurtherModes.scaleDownThreshold` | `DSSimplifiedBarcodeReaderSettings.scaleDownThreshold` |

Please use the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/) to upgrade your template if you are using `initRuntimeSettingsWithFile` or `initRuntimeSettingsWithString`. 

**Useful links**

- [`DSCaptureVisionRouter`]({{ site.dcvb_ios_api }}capture-vision-router/capture-vision-router.html)
- [`DSSimplifiedCaptureVisionSettings`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`DSSimplifiedBarcodeReaderSettings`]({{ site.dbr_ios_api }}simplified-barcode-reader-settings.html)
