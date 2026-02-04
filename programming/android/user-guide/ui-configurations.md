---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader for Android
description: Learn how to add basic UI elements on the DCECameraView for Android edition.
keywords: UI Configurations, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# UI Configurations

In this article, you will learn:

- How to highlight the decoded barcodes
- How to add clickable torchlight button

## Preparations

UI configuring APIs are all included in the [CameraView]({{ site.dce_android }}auxiliary-api/dcecameraview.html) class. All the UI configurations are implemented via the `CameraView` instance. You can use the following steps to get prepared for UI configurations. These steps are also mentioned in the [Getting started](../user-guide.md).

```java
import com.dynamsoft.dce.*;
```

## How to Highlight Decoded Barcodes

Turn on/off the highlight overlay:

```java
// Get the layer first.
DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
// Set the visible property to true or false to control the visibility.
layer.setVisible(true);
```

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

## How to Add a Clickable Torchlight Button

In the `cameraView`, there is a built-in clickable torch button that can control the status of the torchlight. By invoking APIs, you can control the parameters such as position, size and icon of the button.

To display the torch button on the UI:

```java
// If you don't add any styles for the button, the torch will be displayed on the top left corner of the screen.
cameraView.setTorchButtonVisible(true);
```

If you set the position or images to nil value, they will be set to the default value.

```java
// You can change the position, size, and displayed image of the button.
cameraView.setTorchButton(new Point(50,50),50,50,null,null);
```
