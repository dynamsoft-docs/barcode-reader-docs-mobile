---
layout: default-layout
title: EnumPresetTemplate of Dynamsoft Capture Vision Flutter Edition
description: The preset template enumeration of DCV Flutter edition.
keywords: Preset template, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumPresetTemplate
---

# EnumDBRPresetTemplate

`EnumDBRPresetTemplate` is the enumeration of preset barcode setting templates.

```dart
enum EnumPresetTemplate{
    DEFAULT, // The default video barcode decoding settings.
    VIDEO_SINGLE_BARCODE, // The optimized video barcode decoding settings for single barcode decoding.
    VIDEO_SPEED_FIRST, // The optimized video barcode decoding settings when speed is prioritized.
    VIDEO_READ_RATE_FIRST, // The optimized video barcode decoding settings when read-rate is prioritized.
    IMAGE_SPEED_FIRST, // The optimized image barcode decoding settings when speed is prioritized.
    IMAGE_READ_RATE_FIRST, // The optimized image barcode decoding settings when read-rate is prioritized.
    IMAGE_DEFAULT // The default image barcode decoding settings.
}
```

## Related API(s)

- [`DCVBarcodeReader.updateRuntimeSettingsFromTemplate`](barcode-reader.md#updateruntimesettingsfromtemplate)
