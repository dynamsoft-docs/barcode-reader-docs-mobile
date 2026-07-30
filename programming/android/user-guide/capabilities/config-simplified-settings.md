---
layout: default-layout
title: Configuring Simplified Settings - Dynamsoft Barcode Reader Android
description: Learn how to configure simplified settings in the Dynamsoft Barcode Reader Android SDK.
keywords: simplified settings, Android, java, kotlin
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Configure Simplified Settings

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

This page explores how to configure basic image processing settings with [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/simplified-capture-vision-settings.html). The following APIs will be used:

1. `getSimplifiedSettings`: Get the settings of the specified `template`.
2. `updateSettings`: Update the settings to the specified `template`.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CaptureVisionRouter mRouter;
mRouter = new CaptureVisionRouter();
try {
   // Obtain current runtime settings.
   SimplifiedCaptureVisionSettings simplifiedCaptureVisionSettings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   simplifiedCaptureVisionSettings.minImageCaptureInterval = 200;
   simplifiedCaptureVisionSettings.timeout = 200;
   SimplifiedBarcodeReaderSettings simplifiedBarcodeReaderSettings = simplifiedCaptureVisionSettings.barcodeSettings;
   simplifiedBarcodeReaderSettings.barcodeFormatIds = EnumBarcodeFormat.BF_QR_CODE | EnumBarcodeFormat.BF_DATAMATRIX;
   simplifiedBarcodeReaderSettings.expectedBarcodesCount = 1;
   // Update settings. Here you must specify the same template name you used when getting the settings.
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, simplifiedCaptureVisionSettings);
} catch (CaptureVisionRouterException e) {
   throw new RuntimeException(e);
}
```
2. 
```kotlin
val mRouter: CaptureVisionRouter? = CaptureVisionRouter()
try {
   // Obtain current runtime settings.
   val simplifiedCaptureVisionSettings = mRouter?.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES)
   simplifiedCaptureVisionSettings?.minImageCaptureInterval = 200
   simplifiedCaptureVisionSettings?.timeout = 200
   val simplifiedBarcodeReaderSettings = simplifiedCaptureVisionSettings?.barcodeSettings
   simplifiedBarcodeReaderSettings!!.barcodeFormatIds = EnumBarcodeFormat.BF_QR_CODE or EnumBarcodeFormat.BF_DATAMATRIX
   simplifiedBarcodeReaderSettings.expectedBarcodesCount = 1
   // Update settings. Here you must specify the same template name you used when getting the settings.
   mRouter?.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, simplifiedCaptureVisionSettings)
} catch (e: CaptureVisionRouterException) {
   throw RuntimeException(e)
}
```

> [!Note]
> To use the settings you have configured, you must specify the same template name when triggering the `startCapturing` or `capture` methods.
