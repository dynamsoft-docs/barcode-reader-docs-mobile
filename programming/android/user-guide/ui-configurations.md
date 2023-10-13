---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader for Android
description: LLearn how to add basic UI elements on the DCECameraView for Android edition.
keywords: UI Configurations, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: false
permalink: /programming/android/ui-configurations-v9.6.30.html
---

# UI Configurations

In this article, you will learn:

- How to highlight the decoded barcodes
- How to add clickable torchlight button

## Preparations

UI configuring APIs are all included in DCECameraView class. All the UI configurations are implemented via the DCECameraView instance. You can use the following steps to get prepared for UI configurations. These steps are also mentioned in the [Getting started](user-guide.md).

```swift
import DynamsoftCameraEnhancer
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

```java
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Create a new DrawingStyle via the DrawingStyleManager.
int style = DrawingStyleManager.createDrawingStyle(R.color.white, 1.0f,R.color.white,R.color.white);
// Set the newly created DrawingStyle to the layer.
layer.setDefaultStyle(style);
```

## How to Add clickable Torchlight Button

In the `cameraView`, there is a build-in clickable torch button that can control the status of the torchlight. By invoking APIs, you can control the parameters such as position, size and icon of the button.

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
