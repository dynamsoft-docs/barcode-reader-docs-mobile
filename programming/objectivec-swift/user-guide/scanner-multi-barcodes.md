---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Use BarcodeScanner iOS edition to scan multiple barcodes
keywords: Multiple barcodes, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Switch Scanning Modes

This article will show you how to switch between the single barcode scanning mode and the multiple barcodes scanning mode.

## How to Switch Scanning Modes

You can use method `scanningMode` to switch between single-barcode and multi-barcode scanning modes.

- `multiple`: Multi-barcode scanning mode.
- `single`: (Default) Single-barcode scanning mode.

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

**Related APIs**

- [`scanningMode`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#scanningmode)

## Configure the Auto-Stop Conditions

For multi-barcode scanning, there are two automatic stop conditions:

- The number of successfully decoded barcodes reaches the `expectedBarcodesCount`.
- There are no new decoding results for N consecutive frames. The value of N can be set using `maxConsecutiveStableFramesToExit`.

For example. Here we apply the following settings:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.expectedBarcodesCount = 10;
config.maxConsecutiveStableFramesToExit = 15;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.expectedBarcodesCount = 10
config.maxConsecutiveStableFramesToExit = 15
```

If there are at least 10 barcodes decoded, it will stop scanning. Otherwise, it will keep scanning for 15 frames. If there are still no barcodes decoded in the 15 frames, it will stop scanning.

**Related APIs**

- [`expectedBarcodesCount`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#expectedbarcodescount)
- [`maxConsecutiveStableFramesToExit`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#maxconsecutivestableframestoexit)

## Comparisons

If you are looking for a solution to scan large batches of barcodes, please refer to the [`BatchBarcodeScanner`](https://www.dynamsoft.com/use-cases/batch-barcode-scanning/){:target="_blank"}. The `BatchBarcodeScanner` has much higher ability on scanning large number of barcodes. It also provides you a highly interactable UI for result previewing, editing, saving, reusing and sharing.

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
        <td style="vertical-align:text-top">Decodes at lease one barcode that available on the latest frame.</td>
        <td style="vertical-align:text-top">Decodes all barcodes that available on the latest frame.</td>
        <td style="vertical-align:text-top">Decodes all barcodes that available on the latest frame. (TTL Overlap Mode)<br>or<br>Decodes all barcodes that available on the first frame. (TTS Ovarlap Mode)<br>or<br>Decodes all barcodes that ever exists while capturing. (Panorama Mode)</td>
    </tr>
    <tr>
        <td style="vertical-align:text-top">Result</td>
        <td style="vertical-align:text-top">Always returns one barcode result. If decoded more than one barcodes, users will be asked to select one.</td>
        <td style="vertical-align:text-top">All decoded barcodes</td>
        <td style="vertical-align:text-top">All decoded barcodes as well as a PanoramicImage that highlighting all these barcodes on it.</td>
    </tr>
    <tr>
        <td style="vertical-align:text-top">Result Editor</td>
        <td style="vertical-align:text-top">Not available</td>
        <td style="vertical-align:text-top">Not available</td>
        <td style="vertical-align:text-top">Supports the following operations<br>1. Extend the current result with all kinds of available image source.<br>2. Manual input new results or edit the existing results<br>3. Save as history<br>4. Export as file (.png, .csv, etc.)</td>
    </tr>
</table>
