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

### Option 1: Add the Library via Maven

1. Open the file `[App Project Root Path]\app\build.gradle` and add the Maven repository:

   ```groovy
   allprojects {
      repositories {
         maven {
               url "https://download2.dynamsoft.com/maven/aar"
         }
      }
   }
   ```

2. Add the references in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftbarcodereaderbundle:{version-number}'
   }
   ```

   > Note: Please view [user guide](user-guide.md#option-1-add-the-library-via-maven) for the correct version number.

3. Click **Sync Now**. After the synchronization is complete, the SDK is added to the project.

### Option 2: Add the Libraries via Local .aar Files

1. Download the SDK package from the <a href="https://www.dynamsoft.com/barcode-reader/downloads/?utm_source=docs" target="_blank">Dynamsoft Website</a>. After unzipping, you should find a single **aar** file can be found in the **Dynamsoft\Libs** directory:

   - 📄 **DynamsoftBarcodeReaderBundle.aar**
   - 📄 **DynamsoftCaptureVisionRouter.aar**
   - 📄 **DynamsoftCameraEnhancer.aar**
   - 📄 **DynamsoftBarcodeReader.aar**
   - 📄 **DynamsoftCore.aar**
   - 📄 **DynamsoftLicense.aar**
   - 📄 **DynamsoftImageProcessing.aar**
   - 📄 **DynamsoftUtility.aar**

2. Copy the above **aar** file to the target directory such as `[App Project Root Path]\app\libs`

3. Open the file `[App Project Root Path]\app\build.gradle` and add the reference in the dependencies:

   ```groovy
   dependencies {
       implementation fileTree(dir: 'libs', include: ['*.aar'])

        def camerax_version = '1.1.0'
        implementation "androidx.camera:camera-core:$camerax_version"
        implementation "androidx.camera:camera-camera2:$camerax_version"
        implementation "androidx.camera:camera-lifecycle:$camerax_version"
        implementation "androidx.camera:camera-view:$camerax_version"
   }
   ```

### Update your code

#### Option 1. Quick Start With the BarcodeScanner APIs

The following code can popup a `BarcodeScannerActivity` from your starter activity by clicking a button. The `BarcodeScannerActivity` has a preset UI so that you don't need to do any other configurations before start scanning.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
package com.dynamsoft.scansinglebarcode;
import android.os.Bundle;
import android.widget.TextView;
import com.dynamsoft.dbrbundle.ui.BarcodeScanResult;
import com.dynamsoft.dbrbundle.ui.BarcodeScannerActivity;
import com.dynamsoft.dbrbundle.ui.BarcodeScannerConfig;
import com.dynamsoft.core.basic_structures.DSRect;
import androidx.activity.result.ActivityResultLauncher;
import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   private ActivityResultLauncher<BarcodeScannerConfig> launcher;
   @Override
   protected void onCreate(@Nullable Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.activity_main);
          TextView textView = findViewById(R.id.tv_result);
          BarcodeScannerConfig config = new BarcodeScannerConfig();
          config.setLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9");
          launcher = registerForActivityResult(new BarcodeScannerActivity.ResultContract(), result -> {
             if (result.getResultStatus() == BarcodeScanResult.EnumResultStatus.RS_FINISHED && result.getBarcodes() != null) {
                    String content = "Result: format: " + result.getBarcodes()[0].getFormatString() + "\n" + "content: " + result.getBarcodes()[0].getText();
                    textView.setText(content);
             } else if (result.getResultStatus() == BarcodeScanResult.EnumResultStatus.RS_CANCELED) {
                    textView.setText("Scan canceled.");
             }
             if (result.getErrorString() != null && !result.getErrorString().isEmpty()) {
                    textView.setText(result.getErrorString());
             }
          });
          findViewById(R.id.btn_navigate).setOnClickListener(v -> launcher.launch(config));
   }
}
```
1. 
```kotlin
package com.dynamsoft.scansinglebarcodekt
import android.graphics.RectF
import android.os.Bundle
import android.view.View
import android.widget.TextView
import androidx.activity.result.ActivityResultLauncher
import androidx.appcompat.app.AppCompatActivity
import com.dynamsoft.core.basic_structures.DSRect
import com.dynamsoft.dbr.EnumBarcodeFormat
import com.dynamsoft.dbrbundle.ui.BarcodeScanResult
import com.dynamsoft.dbrbundle.ui.BarcodeScannerActivity
import com.dynamsoft.dbrbundle.ui.BarcodeScannerConfig
class MainActivity : AppCompatActivity() {
   private lateinit var launcher: ActivityResultLauncher<BarcodeScannerConfig>
   override fun onCreate(savedInstanceState: Bundle?) {
          super.onCreate(savedInstanceState)
          setContentView(R.layout.activity_main)
          val textView = findViewById<TextView>(R.id.tv_result)
          val config = BarcodeScannerConfig().apply {
             license = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";
          }
          launcher = registerForActivityResult(BarcodeScannerActivity.ResultContract()) { result ->
             if (result.resultStatus == BarcodeScanResult.EnumResultStatus.RS_FINISHED && result.barcodes != null) {
                    val content = """
                    Result: format: ${result.barcodes[0].formatString}
                    content: ${result.barcodes[0].text}
                    """.trimIndent()
                    textView.text = content
             } else if (result.resultStatus == BarcodeScanResult.EnumResultStatus.RS_CANCELED) {
                    textView.text = "Scan canceled."
             }
             if (result.errorString != null && result.errorString.isNotEmpty()) {
                    textView.text = result.errorString
             }
          }
          findViewById<View>(R.id.btn_navigate).setOnClickListener {
             launcher.launch(
                    config
             )
          }
   }
}
```

The template system is upgraded. The template you used for the previous version can't be directly recognized by the new version. Please <a href="https://download2.dynamsoft.com/dcv/TemplateConverter.zip" target="_blank">download the TemplateConverter tool</a> or <a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">contact us</a> to upgrade your template.

[View how to upload you template file via BarcodeScannerConfig.](user-guide/configure-barcode-scanner.md#setup-a-customized-template-file)

#### Option 2. Use Foundation APIs

##### Update the License Activation Code

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

##### Update Single Image Decoding APIs

The APIs for decoding single image has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.decodeFile` | `CaptureVisionRouter.capture(String filePath, String templateName)` |
| `BarcodeReader.decodeFileInMemory` | `CaptureVisionRouter.capture(byte[] fileBytes, String templateName)` |
| `BarcodeReader.decodeBuffer` | `CaptureVisionRouter.capture(ImageData imageData, String templateName)` |
| `BarcodeReader.decodeBufferedImage` | `CaptureVisionRouter.capture(Bitmap bitmap, String templateName)` |
| `class TextResult` | `class BarcodeResultItem` |
| `BarcodeReader.decodeBase64String` | **Currently not available**. |

##### Update Video Streaming Decoding APIs

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

##### Migrate Your Templates

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

##### Migrate Your PublicRuntimeSettings

The class `PublicRuntimeSettings` has been refactored. It retains commonly used properties while removing the previously complex property settings, which are now exclusively supported through templates.

The APIs for accessing and updating `PublicRuntimeSettings` has been adjusted as follows:

| Old APIs | New APIs |
| :----------- | :------- |
| `BarcodeReader.getRuntimeSettings` | `CaptureVisionRouter.getSimplifiedSettings` |
| `BarcodeReader.updateRuntimeSettings` | `CaptureVisionRouter.updateSettings` |

###### Migrate to SimplifiedCaptureVisionSettings

The following properties are replaced by similar properties under `SimplifiedCaptureVisionSettings`. They can also be set via a template file(String).

| PublicRuntimeSettings Property | SimplifiedCaptureVisionSettings Property | Template File Parameter |
| ------------------------------- | ----------------------------------------- | ----------------------- |
| `region` | [`roi`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roi) & [`roiMeasuredInPercentage`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#roimeasuredinpercentage) | [`TargetROIDef.Location.Offset`]({{ site.dcvb_parameters_reference }}target-roi-def/location.html?product=dbr) |
| `timeout` | [`timeout`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#timeout) | [`CaptureVisionTemplates.Timeout`]({{ site.dcvb_parameters_reference }}capture-vision-template/timeout.html?product=dbr) |

###### Migrate to SimplifiedBarcodeReaderSettings

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

###### Migrate to Template File

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

###### Migrate to Other APIs

The `Intermediate Result` system is redesigned and the following properties are deprecated.

| PublicRuntimeSettings Property|
| --------------------- |
| `intermediateResultTypes` |
| `intermediateResultSavingMode` |

###### Removed

The following properties are removed.

| PublicRuntimeSettings Property|
| --------------------- |
| `resultCoordinateType` |

| FurtherModes Property|
| --------------------- |
| `colourClusteringModes` |
