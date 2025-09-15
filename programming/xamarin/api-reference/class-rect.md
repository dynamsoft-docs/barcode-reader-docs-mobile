---
layout: default-layout
title: Class Rect of Dynamsoft Capture Vision Xamarin Edition
description: The interface of Rect
keywords: Class Rect, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Rect
---

# Rect

Class `Rect` stores the rectangle information.

```c#
namespace DCVXamarin
{
    public class Rect
    {
        // A Rect that indicates the location of the torch button.
        // X: The x coordinate of the top-left vertice of the rectangle.
        public double X { get; set; }
        // Y: The y coordinate of the top-left vertice of the rectangle.
        public double Y { get; set; }
        // Width: The width of the rectangle.
        public double Width { get; set; }
        // Height: The height of the rectangle.
        public double Height { get; set; }
    }
}
```
