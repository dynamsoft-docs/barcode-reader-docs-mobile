---
layout: default-layout
title: EnumPresetTemplate - Dynamsoft Capture Vision Router Lite Flutter
description: The enumeration PresetTemplate of Dynamsoft Capture Vision Router describes the preset template.
keywords: CaptureVisionTemplate, EnumPresetTemplate, single barcode template, speed first, read-rate first, template, preset
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: EnumPresetTemplate
---

# EnumPresetTemplate

`EnumPresetTemplate` is an enumeration of preset templates that are configured for different recognition tasks, depending on the functional product as well as the desired performance from that functional product. These strings can be used when specifying template name with the [`startCapturing`](../capture-vision-router/capture-vision-router.md#startcapturing) or [`capture`](../capture-vision-router/capture-vision-router.md#capture) methods of the [`CaptureVisionRouter`](../capture-vision-router/capture-vision-router.md).

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
static class EnumPresetTemplate {
    static const readBarcodes = "ReadBarcodes_Default";
    static const readBarcodesSpeedFirst = "ReadBarcodes_SpeedFirst";
    static const readBarcodesReadRateFirst = "ReadBarcodes_ReadRateFirst";
    static const readSingleBarcode = "ReadSingleBarcode";
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `readBarcodes` | The default template for the Barcode Reader that offers a balance between speed and read rate. |
| `readBarcodesSpeedFirst` | The speed first template prioritizes speed over read rate when reading barcodes. |
| `readBarcodesReadRateFirst` | The read rate first template prioritizes read rate over speed when reading barcodes. |
| `readSingleBarcode` | The single barcode template focuses on the single-scan barcode reading mode and should not be used when reading multiple barcodes at a time as it is more speed focused. |
