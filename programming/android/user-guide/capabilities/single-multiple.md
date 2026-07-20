---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader Android
description: Use BarcodeScanner Android edition to scan multiple barcodes
keywords: Multiple barcodes, Android
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

## Improve Multi-Scan Stability

Use max overlapping feature of multi-frame cross filter to improve the stability of multi-barcode scanning.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CaptureVisionRouter mRouter = new CaptureVisionRouter();
MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
// Default value of MaxOverlapingFrames is 5. Increase the number if you want to further improve the stability.
filter.setMaxOverlappingFrames(EnumCapturedResultItemType.CRIT_BARCODE, 10);
filter.enableLatestOverlapping(EnumCapturedResultItemType.CRIT_BARCODE, true);
mRouter.addResultFilter(filter);
```
2. 
```kotlin
val mRouter: CaptureVisionRouter? = CaptureVisionRouter()
val filter: MultiFrameResultCrossFilter = MultiFrameResultCrossFilter()
// Default value of MaxOverlapingFrames is 5. Increase the number if you want to further improve the stability.
filter.setMaxOverlappingFrames(EnumCapturedResultItemType.CRIT_BARCODE, 10)
filter.enableLatestOverlapping(EnumCapturedResultItemType.CRIT_BARCODE, true)
mRouter?.addResultFilter(filter)
```
