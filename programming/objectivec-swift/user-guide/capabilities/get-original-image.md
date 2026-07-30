---
layout: default-layout
title: Get Original Image - Dynamsoft Barcode Reader iOS
description: Learn how to get the original image that produces the current result in the Dynamsoft Barcode Reader iOS SDK.
keywords: original image, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Get Original Image

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

## Get by HashId (Recommended)

Keep your current result output logic unchanged. Use `originalImageHashId` from `DecodedBarcodesResult` to fetch the original image only when needed.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
   DSImageData *originalImage = [[self.cvr getIntermediateResultManager] getOriginalImage:result.originalImageHashId];
}
```
2. 
```swift
func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
   let originalImage = cvr.getIntermediateResultManager().getOriginalImage(result.originalImageHashId)
}
```

- [`getOriginalImageHashId`]({{ site.dbr_ios_api }}decoded-barcodes-result.html)
- [`getIntermediateResultManager`]({{ site.dcvb_ios_api }}capture-vision-router/intermediate-result.html#getintermediateresultmanager)
- [`getOriginalImage`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/intermediate-result-manager.html#getoriginalimage)

## Include Original Image in Results

Enable original image output in settings so each capture result can directly contain the original image item. This is convenient for downstream processing, but usually adds more data to each result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
DSSimplifiedCaptureVisionSettings *settings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
// Set outputOriginalImage to YES so the original image will be included in DSCapturedResultReceiver.
settings.outputOriginalImage = YES;
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:settings error:&error];
[self.cvr addResultReceiver:self];
- (void)onCapturedResultReceived:(DSCapturedResult *)result {
   if (result.items.count > 1) {
          for (DSCapturedResultItem *item in result.items) {
             if (item.type == DSCapturedResultItemTypeBarcode) {
                // Use barcode result
             } else if (item.type == DSCapturedResultItemTypeOriginalImage) {
                // Use original image
             }
          }
   }
}
```
2. 
```swift
do {
   let settings = try cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   // Set outputOriginalImage to true so the original image will be included in CapturedResultReceiver.
   settings.outputOriginalImage = true
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: settings)
} catch {
}
cvr.addResultReceiver(self)
func onCapturedResultReceived(_ result: CapturedResult) {
   if let items = result.items, items.count > 1
   {
          for item in items {
             if item.type == .barcode {
                // Use barcode result
             } else if item.type == .originalImage {
                // Use original image
             }
          }
   }
}
```

- [`outputOriginalImage`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html#outputoriginalimage)
- [`onCapturedResultReceived`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/captured-result-receiver.html#oncapturedresultreceived)
