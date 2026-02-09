---
layout: default-layout
title: Migrate to v11 - Dynamsoft Barcode Reader for Android
description: Follow this page to learn to upgrade Barcode Reader SDK Android edition to v11.
keywords: updates guide, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Migrate to v11

> [!IMPORTANT]
> **We strongly recommend upgrading to v11.x.** All future algorithm improvements, performance optimizations, and new features will be developed exclusively for v11 and later versions. Version 10.x and earlier will only receive critical bug fixes and will not benefit from ongoing innovation.

## Why Upgrade to v11?

- **Latest Barcode Recognition Algorithms**: Access to cutting-edge decoding algorithms and accuracy improvements
- **Ongoing Performance Enhancements**: Faster processing speeds and better resource optimization
- **New Features & Capabilities**: Future functionality will only be available in v11+
- **Active Development**: Version 11 is the actively maintained branch receiving continuous updates
- **Long-term Support**: Ensure your application stays current with industry standards

**⚠️ Version 10.x is in maintenance mode only** - no new features or algorithm updates will be backported.

## Migrate from v10.x to v11.x

### Update the Libraries

#### Option 1: Add the Library via Maven

1. Open the file `[App Project Root Path]\settings.gradle` and add the Maven repository:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencyResolutionManagement {
      repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
      repositories {
             google()
             mavenCentral()
             maven {
                url "https://download2.dynamsoft.com/maven/aar"
             }
      }
   }
   ```
   2. 
   ```kotlin
   dependencyResolutionManagement {
      repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
      repositories {
             google()
             mavenCentral()
             maven {
                url = uri("https://download2.dynamsoft.com/maven/aar")
             }
      }
   }
   ```

2. Open the file `[App Project Root Path]\app\build.gradle` and add the dependencies:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencies {
      implementation 'com.dynamsoft:barcodereaderbundle:{version-number}'
   }
   ```
   2. 
   ```kotlin
   dependencies {
      implementation("com.dynamsoft:barcodereaderbundle:{version-number}")
   }
   ```

   <div class="blockquote-note"></div>
   > Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.

3. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

#### Option 2: Add the Libraries via Local .aar Files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs#mobile" target="_blank">Dynamsoft Website</a>. After unzipping, several **aar** files can be found in the **Dynamsoft\Libs** directory:

   - 📄 **DynamsoftBarcodeReaderBundle.aar**
   - 📄 **DynamsoftCaptureVisionBundle.aar**

2. Copy the above **.aar** files to the target directory such as *[App Project Root Path]\app\libs*

3. Open the file `[App Project Root Path]\app\build.gradle` and add the reference in the dependencies:

   <div class="sample-code-prefix"></div>
   >- groovy
   >- kts
   >
   >1. 
   ```groovy
   dependencies {
      implementation fileTree(dir: 'libs', include: ['*.aar'])
      def camerax_version = '1.4.2'
      implementation "androidx.camera:camera-core:$camerax_version"
      implementation "androidx.camera:camera-camera2:$camerax_version"
      implementation "androidx.camera:camera-lifecycle:$camerax_version"
      implementation "androidx.camera:camera-view:$camerax_version"
   }
   ```
   2. 
   ```kotlin
   val camerax_version = "1.4.2"
   dependencies {
      implementation(fileTree(mapOf("dir" to "libs", "include" to listOf("*.aar"))))
      implementation("androidx.camera:camera-core:$camerax_version")
      implementation("androidx.camera:camera-camera2:$camerax_version")
      implementation("androidx.camera:camera-lifecycle:$camerax_version")
      implementation("androidx.camera:camera-view:$camerax_version")
   }
   ```

   <div class="blockquote-note"></div>
   > The camera features require the camerax dependencies.

4. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

### Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)

## Migrate from v9.x or earlier

> [!IMPORTANT]
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

### Update the Template File

You can use the template converter to upgrade your template. View the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/)

### API Change Reference List

License activation:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.initLicense` | `LicenseManager.initLicense` |

Process Single Image:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.decodeFile` | `CaptureVisionRouter.capture(String filePath, String templateName)` |
| `BarcodeReader.decodeFileInMemory` | `CaptureVisionRouter.capture(byte[] fileBytes, String templateName)` |
| `BarcodeReader.decodeBuffer` | `CaptureVisionRouter.capture(ImageData imageData, String templateName)` |
| `BarcodeReader.decodeBufferedImage` | `CaptureVisionRouter.capture(Bitmap bitmap, String templateName)` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

Process the video streaming:

| Old APIs | New APIs |
| :------- | :------- |
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

Template and Settings Management:

| Old APIs | New APIs |
| :------- | :------- |
| `BarcodeReader.initRuntimeSettingsWithFile` | `CaptureVisionRouter.initSettingsFromFile` |
| `BarcodeReader.initRuntimeSettingsWithString` | `CaptureVisionRouter.initSettings` |
| `BarcodeReader.outputSettingsToFile` | `CaptureVisionRouter.outputSettingsToFile` |
| `BarcodeReader.outputSettingsToString` | `CaptureVisionRouter.outputSettings` |
| `BarcodeReader.resetRuntimeSettings` | `CaptureVisionRouter.resetSettings` |
| `BarcodeReader.appendTplFileToRuntimeSettings` | **Not available**. |
| `BarcodeReader.appendTplStringToRuntimeSettings` | **Not available**. |
| `BarcodeReader.getRuntimeSettings` | `CaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `CaptureVisionRouter.updateSettings` |
| `PublicRuntimeSettings.region` | `SimplifiedCaptureVisionSettings.roi` & `SimplifiedCaptureVisionSettings.roiMeasuredInPercentage` |
| `PublicRuntimeSettings.timeout` | `SimplifiedCaptureVisionSettings.timeout` |
| `PublicRuntimeSettings.minBarcodeTextLength` | `SimplifiedBarcodeReaderSettings.minBarcodeTextLength` |
| `PublicRuntimeSettings.minResultConfidence` | `SimplifiedBarcodeReaderSettings.minResultConfidence` |
| `PublicRuntimeSettings.localizationModes` | `SimplifiedBarcodeReaderSettings.localizationModes` |
| `PublicRuntimeSettings.expectedBarcodesCount` | `SimplifiedBarcodeReaderSettings.expectedBarcodesCount` |
| `PublicRuntimeSettings.barcodeFormatIds` | `SimplifiedBarcodeReaderSettings.barcodeFormatIds` |
| `PublicRuntimeSettings.barcodeFormatIds_2` | `SimplifiedBarcodeReaderSettings.barcodeFormatIds` |
| `PublicRuntimeSettings.deblurModes` | `SimplifiedBarcodeReaderSettings.deblurModes` |
| `PublicRuntimeSettings.deblurLevel` | **Not available**, use `SimplifiedBarcodeReaderSettings.deblurLevel`. |
| `PublicRuntimeSettings.maxAlgorithmThreadCount` | `SimplifiedBarcodeReaderSettings.maxThreadsInOneTask` |
| `FurtherModes.grayscaleTransformationModes` | `SimplifiedBarcodeReaderSettings.grayscaleTransformationModes` |
| `FurtherModes.imagePreprocessingModes` | `SimplifiedBarcodeReaderSettings.grayscaleEnhancementModes` |
| `FurtherModes.scaleDownThreshold` | `SimplifiedBarcodeReaderSettings.scaleDownThreshold` |

Please use the [online template converter](https://www.dynamsoft.com/tools/template-upgrade/) to upgrade your template if you are using `initRuntimeSettingsWithFile` or `initRuntimeSettingsWithString`. 

**Useful links**

- [`CaptureVisionRouter`]({{ site.dcvb_android_api }}capture-vision-router/capture-vision-router.html)
- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`SimplifiedBarcodeReaderSettings`]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html)
