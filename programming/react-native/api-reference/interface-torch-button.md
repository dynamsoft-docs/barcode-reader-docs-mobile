---
layout: default-layout
title: Interface TorchButton - Dynamsoft Capture Vision React Native Edition
description: The interface of torch button
keywords: Interface TorchButton, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: TorchButton
---

# TorchButton

Interface `TorchButton`.

```js
export interface TorchButton {
    /**
     * The location of the torch button. Vew interface Rect for more information.
     */
    location: Rect;
    /**
     * Whether the button is visible.
     */
    visible: boolean;
    /**
     * The torch image when the torch is on.
     */
    torchOnImageBase64: string;
    /**
     * The torch image when the torch is off.
     */
    torchOffImageBase64: string;
}
```

## Related API(s)

- [`Interface Rect`](interface-rect.md)
