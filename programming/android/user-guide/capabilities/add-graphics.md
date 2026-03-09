---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader Android
description: Learn how to add basic UI elements on the DCECameraView for Android edition.
keywords: UI Configurations, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# UI Configurations

> [!Important]
> Features on this page are only available for the **Foundational APIs**.

`CameraView` allows you to define your own graphics diplaying rules with the `Drawing` APIs.

- `DrawingItem`: Graphics or other UI elements.
- `DrawingLayer`: The layer for displaying the `DrawingItems`.
- `DrawingStyle`: The style for the `DrawingItem`.

## How to Hide Default Barcode Highlight Overlay

Barcode highlight overlay is displayed by default. You can set the layer invisible to disable it:

```java
// Get the layer first.
DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
// Set the visible property to true or false to control the visibility.
layer.setVisible(true);
```

## How to Add User Defined DrawingItem(s)

## How to Change the DrawingStyle

Set the style of the highlight overlays with a preset style:

```java
// Get the layer first.
DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
// Change the style of the layer.
layer.setDefaultStyle(DrawingStyleManager.STYLE_BLUE_STROKE);
```

Set the style of the highlight overlays with a use defined style:

1. Create colours in the **values/colours.xml** file.

    ```xml
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_200_transparent">#2003DAC5</color>
    ```

2. Create your style with the colour and set to the layer.

    ```java
    // Get the layer first.
    DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
    // Create a new DrawingStyle via the DrawingStyleManager.
    int teal_200_transparent = ResourcesCompat.getColor(MainActivity.this.getResources(), R.color.teal_200_transparent, null);
    int teal_200 = ResourcesCompat.getColor(MainActivity.this.getResources(), R.color.teal_200, null);
    int style = DrawingStyleManager.createDrawingStyle(teal_200, 1.0f,teal_200_transparent,teal_200);
    // Set the newly created DrawingStyle to the layer.
    layer.setDefaultStyle(style);
    ```
