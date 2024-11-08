---
layout: default-layout
title: EnumPresetTemplate - Dynamsoft Capture Vision Router Lite MAUI
description: The enumeration PresetTemplate of Dynamsoft Vision Router describes the preset template.
keywords: CaptureVisionTemplate, PresetTemplate, single barcode template, speed first, read-rate first
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: PresetTemplate
---

# EnumPresetTemplate

`EnumPresetTemplate` class defines the preset tempate strings. These strings can be used when specifying template name with [`StartCapturing`](../multiple-file-processing.md#startcapturing) or [`Capture`](../single-file-processing.md#capture) methods.

## Definition

*Namespace:* Dynamsoft.CaptureVisionRouter.Maui

*Assembly:* Dynamsoft.CaptureVisionRouterLite.Maui

```csharp
public class EnumPresetTemplate
{
    public const string PT_DEFAULT = "Default";
    public const string PT_READ_BARCODES = "ReadBarcodes_Default";
    public const string PT_READ_BARCODES_SPEED_FIRST = "ReadBarcodes_SpeedFirst";
    public const string PT_READ_BARCODES_READ_RATE_FIRST = "ReadBarcodes_ReadRateFirst";
    public const string PT_READ_SINGLE_BARCODE = "ReadSingleBarcode";
}
```
