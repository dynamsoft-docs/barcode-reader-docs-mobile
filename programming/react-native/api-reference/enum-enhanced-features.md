---
layout: default-layout
title: EnumEnhancedFeatures - Dynamsoft Capture Vision React Native Edition
description: Enhanced camera features of DCV React Native edition.
keywords: Enhanced features, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumEnhancedFeatures
---

# EnumEnhancedFeatures

`EnumEnhancedFeatures` is the enumeration of enhanced camera features.

```js
enum EnumEnhancedFeatures{
    EF_FRAME_FILTER = 1, // The default video barcode decoding settings.
    EF_SENSOR_CONTROL = 2, // The optimized video barcode decoding settings for single barcode decoding.
    EF_ENHANCED_FOCUS = 4, // The optimized video barcode decoding settings when speed is prioritized.
    EF_AUTO_ZOOM = 16, // The optimized image barcode decoding settings when speed is prioritized.
    EF_SMART_TORCH = 32, // The optimized image barcode decoding settings when read-rate is prioritized.
    EF_ALL = 63 // The default image barcode decoding settings.
}
```
