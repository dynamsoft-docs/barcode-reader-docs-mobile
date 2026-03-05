---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Use BarcodeScanner Android edition to scan multiple barcodes
keywords: Multiple barcodes, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Single & Multiple Barcode Scanning

This article explains how to switch between single-barcode scanning mode and multi-barcode scanning mode.

## Work with BarcodeScanner APIs

### How to Switch Scanning Modes

Use the `setScanningMode` method to switch between single-barcode and multi-barcode scanning modes.

- `SM_MULTIPLE`: Multi-barcode scanning mode.
- `SM_SINGLE`: (Default) Single-barcode scanning mode.

**Code Snippet**

```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setScanningMode(EnumScanningMode.SM_MULTIPLE);
```

### Configure the Auto-Stop Conditions

For multi-barcode scanning, there are two automatic stop conditions:

- The number of successfully decoded barcodes reaches the `expectedBarcodesCount`.
- There are no new decoding results for N consecutive frames. The value of N can be set using `setMaxConsecutiveStableFramesToExit`.

For example, apply the following settings:

```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setScanningMode(EnumScanningMode.SM_MULTIPLE);
config.setExpectedBarcodesCount(10);
config.setMaxConsecutiveStableFramesToExit(15);
```

If at least 10 barcodes are decoded, scanning stops. Otherwise, scanning continues for up to 15 consecutive stable frames. If no new decoding results are found within those 15 frames, scanning stops.

**Related APIs**

- [`setScanningMode`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanningmode)
- [`setExpectedBarcodesCount`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setexpectedbarcodescount)
- [`setMaxConsecutiveStableFramesToExit`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setmaxconsecutivestableframestoexit)

## Work with Foundational APIs

### Configure Expected Barcodes Count

- `expectedBarcodesCount` = 1: Scan a single barcode.
- `expectedBarcodesCount` = 0: Allows the library to return more than one result, but it does not aggressively optimize for decoding multiple barcodes.
- `expectedBarcodesCount` = 999 or any other number: Makes every effort to decode up to the specified number of barcodes, when possible.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CaptureVisionRouter mRouter;
mRouter = new CaptureVisionRouter();
try {
   SimplifiedCaptureVisionSettings simplifiedCaptureVisionSettings = mRouter.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES);
   SimplifiedBarcodeReaderSettings simplifiedBarcodeReaderSettings = simplifiedCaptureVisionSettings.barcodeSettings;
   simplifiedBarcodeReaderSettings.expectedBarcodesCount = 1;
   mRouter.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, simplifiedCaptureVisionSettings);
} catch (CaptureVisionRouterException e) {
   throw new RuntimeException(e);
}
```
2. 
```kotlin
val mRouter: CaptureVisionRouter? = CaptureVisionRouter()
try {
   val simplifiedCaptureVisionSettings = mRouter?.getSimplifiedSettings(EnumPresetTemplate.PT_READ_BARCODES)
   val simplifiedBarcodeReaderSettings = simplifiedCaptureVisionSettings?.barcodeSettings
   simplifiedBarcodeReaderSettings.expectedBarcodesCount = 1
   mRouter?.updateSettings(EnumPresetTemplate.PT_READ_BARCODES, simplifiedCaptureVisionSettings)
} catch (e: CaptureVisionRouterException) {
   throw RuntimeException(e)
}
```

**Related APIs**

- [`simplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html)
- [`simplifiedBarcodeReaderSettings`]({{ site.dbr_android_api }}simplified-barcode-reader-settings.html)

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
