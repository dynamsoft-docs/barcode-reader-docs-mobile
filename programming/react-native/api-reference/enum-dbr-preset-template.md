---
layout: default-layout
title: EnumPresetTemplate - Dynamsoft Capture Vision React Native Edition
description: The preset template enumeration of DCV React Native edition.
keywords: Preset template, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumPresetTemplate
---

# EnumDBRPresetTemplate

`EnumDBRPresetTemplate` is the enumeration of preset barcode setting templates.

```js
enum EnumPresetTemplate{
    DEFAULT = 0, // The default video barcode decoding settings.
    VIDEO_SINGLE_BARCODE = 1, // The optimized video barcode decoding settings for single barcode decoding.
    VIDEO_SPEED_FIRST = 2, // The optimized video barcode decoding settings when speed is prioritized.
    VIDEO_READ_RATE_FIRST = 3, // The optimized video barcode decoding settings when read-rate is prioritized.
    IMAGE_SPEED_FIRST = 4, // The optimized image barcode decoding settings when speed is prioritized.
    IMAGE_READ_RATE_FIRST = 5, // The optimized image barcode decoding settings when read-rate is prioritized.
    IMAGE_DEFAULT = 6 // The default image barcode decoding settings.
}
```
