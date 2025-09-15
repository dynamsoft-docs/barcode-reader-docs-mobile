---
layout: default-layout
title: EnumPresetTemplate of Dynamsoft Capture Vision Xamarin Edition
description: The preset template enumeration of DCV Xamarin edition.
keywords: Preset template, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumPresetTemplate
---

# EnumDBRPresetTemplate

`EnumDBRPresetTemplate` is the enumeration of preset barcode setting templates.

```c#
namespace DCVXamarin
{
    public enum EnumDBRPresetTemplate : long
    {
        DEFAULT = 0,
        VIDEO_SINGLE_BARCODE = 1,
        VIDEO_SPEED_FIRST = 2,
        VIDEO_READ_RATE_FIRST = 3,
        IMAGE_SPEED_FIRST = 4,
        IMAGE_READ_RATE_FIRST = 5,
        IMAGE_DEFAULT = 6
    }
}
```

## Related API(s)

- [`IDCVBarcodeReader.updateRuntimeSettingsFromTemplate`](barcode-reader.md#updateruntimesettingsfromtemplate)
