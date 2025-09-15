---
layout: default-layout
title: EnumCameraPosition - Dynamsoft Capture Vision React Native Edition
description: The enumeration for user to select camera.
keywords: Barcode format, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumCameraPosition
---

# EnumCameraPosition

`EnumCameraPosition` is the enumeration for user to select camera.

```js
enum EnumCameraPosition {
    /**
     * The default back-facing camera. It is a wide-angle camera for general usage.
     */
    CP_BACK = 0,
    /**
     * The front-facing camera.
     */
    CP_FRONT = 1,
    /**
     * The back-facing ultra-wide-angle camera. It is an ultra-wide-angle camera for macro-distance capturing.
     */
    CP_BACK_ULTRA_WIDE = 2,
    /**
     * A back-facing virtual camera. It is a vitural camera that can switch between the wide-angle camera and the ultra-wide-angle camera automatically.
     * Supported devices include: iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15 Pro, iPhone 15 Pro Max.
     */
    CP_BACK_DUAL_WIDE_AUTO = 3
}
```

## Related API(s)

- [`DCVCameraView.cameraPosition`](camera-view.md#cameraposition)
