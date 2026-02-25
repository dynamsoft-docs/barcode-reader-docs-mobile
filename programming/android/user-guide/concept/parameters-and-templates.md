---
layout: default-layout
title: Parameters & Settings - Dynamsoft Barcode Reader for Android User Guide
description: This page explores how to use the parameters and settings with Dynamsoft Barcode Reader Android SDK.
keywords: user guide, parameters, settings, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Parameters, Settings & Templates

- `Parameteres`: Algorithm `parameters` that determines how to process the images.
- `Settings`: APIs for you to quickly access the `parameters`.
- `Templates`: JSON objects that can define all available `parameters`.
- `Preset Templates`: Quick-start templates. Available via `EnumPresetTemplate`.
- `Customized Templates`: Customized templates in a JSON file.

### When to use Settings

Settings are intergated under `SimplifiedCaptureVisionSettings`, which is a subset of the parameter template. Simple and common parameters are available in `SimplifiedCaptureVisionSettings` so that you can quickly access the parameters.

Available settings:

- Barcode formats
- Expected barcodes count
- ROI
- Timeout
- Image capture interval

Generally, settings are used together with `Preset Templates`.

Common Steps:

1. Select a `Preset Template`.
2. Minor optimization with `SimplifiedCaptureVisionSettings`.

### When to use a Customized Templates

If you are not satisfied with the curent performance, you can contact us for a fully customization. Then, you receive a customized template.

### Next Step

- [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/simplified-capture-vision-settings.html) API references
- How to use customized templates - [initSettingsFromFile]({{ site.dcvb_android_api }}capture-vision-router/settings.html#initsettingsfromfile)

<!-- 
`SimplifiedCaptureVisionSettings` is a subset of the parameter template for users to quickly access.

| SimplifiedCaptureVisionSettings |
| ------------------------------- |
| *Quadrilateral* roi<br>*int* minImageCaptureInterval<br>*int* maxParallelTasks<br>*int* timeout<br>*SimplifiedBarcodeReaderSettings* barcodeSettings<br>…… |

Typical barcode decoding parameters are available in `SimplifiedBarcodeReaderSettings`, which you can access via `SimplifiedCaptureVisionSettings.barcodeSettings`.

| SimplifiedBarcodeReaderSettings |
| ------------------------------- |
| *long* barcodeFormatIds<br>*int* expectedBarcodesCount<br>*int[]* localizationModes<br>*int[]* deblurModes<br>*int[]* grayscaleTransformationModes<br>*String* barcodeTextRegExPattern<br>…… |

The steps to use `SimplifiedCaptureVisionSettings` are as follows:

1. Get the `SimplifiedCaptureVisionSettings` object via [`DynamsoftCaptureVisionRouter.getSimplifiedSettings`]({{ site.dcvb_android_api }}capture-vision-router/settings.html).
2. Configure the simplified settings object.
3. Update the settings via `updateSettings`.

```java
try {
    // Here we use preset template PT_READ_BARCODES as an example.
    SimplifiedCaptureVisionSettings simplifiedCaptureVisionSettings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
    simplifiedCaptureVisionSettings.minImageCaptureInterval = 200;
    simplifiedCaptureVisionSettings.timeout = 200;
    SimplifiedBarcodeReaderSettings simplifiedBarcodeReaderSettings = simplifiedCaptureVisionSettings.barcodeSettings;
    simplifiedBarcodeReaderSettings.barcodeFormatIds = EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_DATAMATRIX;
    simplifiedBarcodeReaderSettings.expectedBarcodesCount = 1;
    simplifiedBarcodeReaderSettings.localizationModes = new int[]{EnumLocalizationMode.LM_CONNECTED_BLOCKS,EnumLocalizationMode.LM_NEURAL_NETWORK};
    simplifiedBarcodeReaderSettings.deblurModes = new int[]{EnumDeblurMode.DM_BASED_ON_LOC_BIN, EnumDeblurMode.DM_DIRECT_BINARIZATION, EnumDeblurMode.DM_DEEP_ANALYSIS};
    simplifiedBarcodeReaderSettings.grayscaleTransformationModes = new int[]{EnumGrayscaleTransformationMode.GTM_ORIGINAL,EnumGrayscaleTransformationMode.GTM_INVERTED};
    // You must trigger the updateSettings method to confirm the changes.
    mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, simplifiedCaptureVisionSettings);
} catch (CaptureVisionRouterException e) {
    throw new RuntimeException(e);
}
```

> [!Important]
> The same `templateName` should be used in `getSimplifiedSettings`, `updateSettings` and `startCapturing` methods.

```java
mRouter.startCapturing(EnumPresetTemplate.PT_READ_BARCODES, new CompletionListener() {
    @Override
    public void onSuccess() {

    }

    @Override
    public void onFailure(int errorCode, String errorString) {

    }
});
``` -->
<!-- 
## How to Use a Template

Add a **Templates** folder to the assets folder of your project at **src\main\assets\Templates**. Put your JSON file in the **Templates** folder. Here we use a **ReadQRCodes.json** file as an example.

<div align="left">
   <p><img src="../../../assets/init-settings-from-file-android.png" alt="initSettings" width="50%" /></p>
   <p>Template Example</p>
</div>

Add the following code to initialize the template:

```java
try {
    mRouter.initSettingsFromFile("ReadQRCodes.json");
} catch (CaptureVisionRouterException e) {
    throw new RuntimeException(e);
}
```

To use your template, you have to specify the template name in the `startCapturing` or `capture` method. The template name is the name of `CaptureVisionTemplates` in your template file (see in the image of step 3).

For example:

```java
mRouter.startCapturing("ReadQRCodes", new CompletionListener() {
    @Override
    public void onSuccess() {
        // Add code to run when the capture is successfully started.
    }

    @Override
    public void onFailure(int errorCode, String errorString) {
        // Add code to run when the capture fails.
    }
});
``` -->
