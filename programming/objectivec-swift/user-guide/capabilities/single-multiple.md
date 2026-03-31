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

## Work with Foundational APIs

### Configure Expected Barcodes Count

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

### Improve Multi-Scan Stability

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

## Work with BarcodeScanner APIs

### How to Switch Scanning Modes

Use the `setScanningMode` method to switch between single-barcode and multi-barcode scanning modes.

- `SM_MULTIPLE`: Multi-barcode scanning mode.
- `SM_SINGLE`: (Default) Single-barcode scanning mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.scanningMode = DSScanningModeMultiple;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.scanningMode = .multiple
```

### Configure the Auto-Stop Conditions

For multi-barcode scanning, there are two automatic stop conditions:

- The number of successfully decoded barcodes reaches the `expectedBarcodesCount`.
- There are no new decoding results for N consecutive frames. The value of N can be set using `setMaxConsecutiveStableFramesToExit`.

For example, apply the following settings:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.scanningMode = DSScanningModeMultiple;
config.expectedBarcodesCount = 10;
config.maxConsecutiveStableFramesToExit = 15;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.scanningMode = .multiple
config.expectedBarcodesCount = 10
config.maxConsecutiveStableFramesToExit = 15
```

If at least 10 barcodes are decoded, scanning stops. Otherwise, scanning continues for up to 15 consecutive stable frames. If no new decoding results are found within those 15 frames, scanning stops.

**Related APIs**

- [`setScanningMode`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setscanningmode)
- [`setExpectedBarcodesCount`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setexpectedbarcodescount)
- [`setMaxConsecutiveStableFramesToExit`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setmaxconsecutivestableframestoexit)

## Comparisons

If you are looking for a solution to scan large batches of barcodes, refer to [`BatchBarcodeScanner`](https://www.dynamsoft.com/use-cases/batch-barcode-scanning/){:target="_blank"}. `BatchBarcodeScanner` is much more capable of large-volume barcode scanning and provides a highly interactive UI for previewing, editing, saving, reusing, and sharing results.

<table style = "text-align:left">
    <thead>
        <tr>
            <th nowrap="nowrap"></th>
            <th nowrap="nowrap">BarcodeScanner Single Mode</th>
            <th nowrap="nowrap">BarcodeScanner Multi Mode</th>
            <th nowrap="nowrap">BatchBarcodeScanner</th>
        </tr>
    </thead>
    <tr>
        <td style="vertical-align:text-top">Dependencies</td>
        <td style="vertical-align:text-top">DynamsoftBarcodeReaderBundle</td>
        <td style="vertical-align:text-top">DynamsoftBarcodeReaderBundle</td>
        <td style="vertical-align:text-top">DynamsoftBatchBarcodeReaderBundle</td>
    </tr>
    <tr>
        <td style="vertical-align:text-top">Scan Ability</td>
        <td style="vertical-align:text-top">Decodes at least one barcode available in the latest frame.</td>
        <td style="vertical-align:text-top">Decodes all barcodes available in the latest frame.</td>
        <td style="vertical-align:text-top">Decodes all barcodes available in the latest frame (TTL Overlap Mode)<br>or<br>decodes all barcodes available in the first frame (TTS Overlap Mode)<br>or<br>decodes all barcodes that appear during capture (Panorama Mode).</td>
    </tr>
    <tr>
        <td style="vertical-align:text-top">Result</td>
        <td style="vertical-align:text-top">Always returns one barcode result. If more than one barcode is decoded, users are asked to select one.</td>
        <td style="vertical-align:text-top">All decoded barcodes</td>
        <td style="vertical-align:text-top">All decoded barcodes, plus a PanoramicImage that highlights all of them.</td>
    </tr>
    <tr>
        <td style="vertical-align:text-top">Result Editor</td>
        <td style="vertical-align:text-top">Not available</td>
        <td style="vertical-align:text-top">Not available</td>
        <td style="vertical-align:text-top">Supports the following operations<br>1. Extend the current result with all available image sources.<br>2. Manually add new results or edit existing results.<br>3. Save to history.<br>4. Export as files (.png, .csv, etc.).</td>
    </tr>
</table>
