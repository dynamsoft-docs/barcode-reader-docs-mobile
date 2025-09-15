---
layout: default-layout
title: Interface TorchButton of Dynamsoft Capture Vision Cordova Edition
description: Documentation page of interface of TorchButton of Dynamsoft Capture Vision.
keywords: Interface TorchButton, API Reference, Cordova
needAutoGenerateSidebar: false
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: TorchButton
---

# TorchButton

Interface `TorchButton` stores the torch button configurations.

```js
export interface TorchButton {
    // A Rect that indicates the location of the torch button.
    // X: The x coordinate of the top-left vertice of the rectangle.
    // Y: The y coordinate of the top-left vertice of the rectangle.
    // Width: The width of the rectangle.
    // Height: The height of the rectangle.
    location: Rect;

    // Whether the torch button is visible.
    // True: visible.
    // False: invisible.
    visible: boolean;

    // When the torch is on, this image will be displayed as the torch image.
    // Input the file path to specify the torch image.
    torchOnImage: string;
    
    // When the torch is off, this image will be displayed as the torch image.
    // Input the file path to specify the torch image.
    torchOffImage: string;
}
```

## Related API(s)

- [`DCVCameraView.setTorchButton`](camera-view.md#settorchbutton)
- [`Interface TorchButton`](interface-torch-button.md)
