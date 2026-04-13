---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader Android
description: Learn how to add basic UI elements on the DCECameraView for Android edition.
keywords: UI Configurations, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Customize Overly with DrawingItems

`CameraView` allows you to define your own graphics diplaying rules with the `Drawing` APIs.

- `DrawingItem`: Graphics or other UI elements.
- `DrawingLayer`: The layer for displaying the `DrawingItems`.
- `DrawingStyle`: The style for the `DrawingItem`.

## Hide Barcode Highlight Overlay

Barcode highlight overlay is displayed by default. You can set the layer invisible to disable it:

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
// Get the layer first.
DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
// Set the visible property to true or false to control the visibility.
layer.setVisible(false);
```
2. 
```kotlin
// Get the layer first.
val layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID)
// Set the visible property to true or false to control the visibility.
layer.setVisible(false)
```

## Add User-Define DrawingItem(s)

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
DrawingLayer barcodeLayer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
ArrayList<DrawingItem> drawingItemArrayList = new ArrayList<>();
QuadDrawingItem quadDrawingItem = new QuadDrawingItem(...);
drawingItemArrayList.add(quadDrawingItem);
barcodeLayer.setDrawingItems(drawingItemArrayList);
// You can also use the append logic if you don't want to clear the previous items.
// barcodeLayer.addDrawingItems(drawingItemArrayList);
```
2. 
```kotlin
val barcodeLayer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID)
val drawingItemArrayList = ArrayList<DrawingItem>()
val quadDrawingItem = QuadDrawingItem(...)
drawingItemArrayList.add(quadDrawingItem)
barcodeLayer.setDrawingItems(drawingItemArrayList)
// You can also use the append logic if you don't want to clear the previous items.
// barcodeLayer.addDrawingItems(drawingItemArrayList)
```

## How to Change the DrawingStyle

### Use Preset Styles

Set the style of the highlight overlays with a preset style:

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
// Get the layer first.
DrawingLayer layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID);
// Change the style of the layer.
layer.setDefaultStyle(DrawingStyleManager.STYLE_BLUE_STROKE);
```
2. 
```kotlin
// Get the layer first.
val layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID)
// Change the style of the layer.
layer.setDefaultStyle(DrawingStyleManager.STYLE_BLUE_STROKE)
```

### Use User Defined Styles

Set the style of the highlight overlays with a user defined style:

1. Create colours in the **values/colours.xml** file.

    ```xml
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_200_transparent">#2003DAC5</color>
    ```

2. Create your style with the colour and set to the layer.

    <div class="sample-code-prefix"></div>
    >- Java
    >- Kotlin
    >
    >1. 
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
    2. 
    ```kotlin
    val layer = cameraView.getDrawingLayer(DrawingLayer.DBR_LAYER_ID)
    // Create a new DrawingStyle via the DrawingStyleManager.
    val teal_200_transparent = ResourcesCompat.getColor(this@MainActivity.getResources(), R.color.teal_200_transparent, null)
    val teal_200 = ResourcesCompat.getColor(this@MainActivity.getResources(), R.color.teal_200, null)
    val style = DrawingStyleManager.createDrawingStyle(teal_200, 1.0f, teal_200_transparent, teal_200)
    // Set the newly created DrawingStyle to the layer.
    layer.setDefaultStyle(style)
    ```
