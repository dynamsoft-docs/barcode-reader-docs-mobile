---
layout: default-layout
title: Configuring Simplified Settings - Dynamsoft Barcode Reader iOS
description: Learn how to configure simplified settings in the Dynamsoft Barcode Reader iOS SDK.
keywords: simplified settings, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# How to Configure Simplified Settings

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

This page explores how to configure basic image processing settings with [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_ios_api }}capture-vision-router/simplified-capture-vision-settings.html). The following APIs will be used:

1. `getSimplifiedSettings`: Get the settings of the specified `template`.
2. `updateSettings`: Update the settings to the specified `template`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
DSSimplifiedCaptureVisionSettings *captureVisionSettings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
captureVisionSettings.minImageCaptureInterval = 200;
captureVisionSettings.timeout = 200;
captureVisionSettings.barcodeSettings.barcodeFormatIds = DSBarcodeFormatQRCode | DSBarcodeFormatDataMatrix;
captureVisionSettings.barcodeSettings.expectedBarcodesCount = 1;
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:captureVisionSettings error:&error];
```
2. 
```swift
guard let captureVisionSettings = try? cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue) else {
   return
}
captureVisionSettings.minImageCaptureInterval = 200
captureVisionSettings.timeout = 200
captureVisionSettings.barcodeSettings?.barcodeFormatIds = [.qrCode, .dataMatrix]
captureVisionSettings.barcodeSettings?.expectedBarcodesCount = 1
do {
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: captureVisionSettings)
} catch {
   // Handle error
}
```

> [!Note]
> To use the settings you have configured, you must specify the same template name when triggering the `startCapturing` or `capture` methods.
