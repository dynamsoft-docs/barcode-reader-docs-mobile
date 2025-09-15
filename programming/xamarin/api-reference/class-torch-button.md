---
layout: default-layout
title: Class TorchButton of Dynamsoft Capture Vision Xamarin Edition
description: The interface of TorchButton
keywords: Interface TorchButton, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: TorchButton
---

# TorchButton

Class `TorchButton` stores the torch button configurations.

```c#
namespace DCVXamarin
{
    public class TorchButton
    {
        // A Rect that indicates the location of the torch button.
        // X: The x coordinate of the top-left vertice of the rectangle.
        // Y: The y coordinate of the top-left vertice of the rectangle.
        // Width: The width of the rectangle.
        // Height: The height of the rectangle.
        public Rect Location;

        // Whether the torch button is visible.
        // True: visible.
        // False: invisible.
        public bool Visible;

        // When the torch is on, this image will be displayed as the torch image.
        public string TorchOnImageBase64;

        // When the torch is off, this image will be displayed as the torch image.
        public string TorchOffImageBase64;
    }
}
```
