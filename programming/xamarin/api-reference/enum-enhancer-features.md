---
layout: default-layout
title: EnumEnhancerFeatures of Dynamsoft Capture Vision Xamarin Edition
description: The enumeration of camera enhancer features
keywords: Camera enhancer features, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumEnhancerFeatures
---

# EnumEnhancerFeatures

`EnumEnhancerFeatures` is the enumeration of advanced features of Dynamsoft Camera Ehancer.

```c#
namespace DCVXamarin
{
    public enum EnumEnhancerFeatures: long
    {
        EF_FRAME_FILTER = 1,
        EF_SENSOR_CONTROL = 2,
        EF_ENHANCED_FOCUS = 4,
        EF_FAST_MODE= 8,
        EF_AUTO_ZOOM = 16,
        EF_SMART_TORCH = 32,
        EF_ALL = 63
    }
}
```
