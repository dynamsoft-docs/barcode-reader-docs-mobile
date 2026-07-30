---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader iOS
description: Use BarcodeScanner iOS edition to scan multiple barcodes
keywords: Multiple barcodes, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Single & Multiple Barcode Scanning

This article explains how to switch between single-barcode scanning mode and multi-barcode scanning mode.


## Configure Expected Barcodes Count

- `expectedBarcodesCount` = 1: Scan a single barcode.
- `expectedBarcodesCount` = 0: Allows the library to return more than one result, but it does not aggressively optimize for decoding multiple barcodes.
- `expectedBarcodesCount` = 999 or any other number: Makes every effort to decode up to the specified number of barcodes, when possible.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError *error = nil;
DSSimplifiedCaptureVisionSettings *captureVisionSettings = [self.cvr getSimplifiedSettings:DSPresetTemplateReadBarcodes error:&error];
captureVisionSettings.barcodeSettings.expectedBarcodesCount = 1;
[self.cvr updateSettings:DSPresetTemplateReadBarcodes settings:captureVisionSettings error:&error];
```
2. 
```swift
guard let captureVisionSettings = try? cvr.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue) else {
   return
}
captureVisionSettings.barcodeSettings?.expectedBarcodesCount = 1
do {
   try cvr.updateSettings(PresetTemplate.readBarcodes.rawValue, settings: captureVisionSettings)
} catch {
}
```

**Related APIs**

- [`simplifiedCaptureVisionSettings`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`simplifiedBarcodeReaderSettings`]({{ site.dbr_ios_api }}simplified-barcode-reader-settings.html)

## Improve Multi-Scan Stability

Use max overlapping feature of multi-frame cross filter to improve the stability of multi-barcode scanning.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSMultiFrameResultCrossFilter *filter = [[DSMultiFrameResultCrossFilter alloc] init];
// Default value of MaxOverlapingFrames is 5. Increase the number if you want to further improve the stability.
[filter setMaxOverlappingFrames:DSCapturedResultItemTypeBarcode frames:10];
[filter enableLatestOverlapping:DSCapturedResultItemTypeBarcode isEnabled:YES];
[self.cvr addResultFilter:filter];
```
2. 
```swift
let filter = MultiFrameResultCrossFilter()
// Default value of MaxOverlapingFrames is 5. Increase the number if you want to further improve the stability.
filter.setMaxOverlappingFrames(.barcode, frames: 10)
filter.enableLatestOverlapping(.barcode, isEnabled: true)
cvr.addResultFilter(filter)
```
