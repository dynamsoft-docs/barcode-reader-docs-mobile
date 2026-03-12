---
layout: default-layout
title: UI Configurations - Dynamsoft Barcode Reader iOS
description: Learn how to add basic UI elements on the DCECameraView for iOS edition.
keywords: UI Configurations, iOS
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Set the visible property to true or false to control the visibility.
layer.visible = true;
```
2. 
```swift
// Get the layer first.
let layer = cameraView.getDrawingLayer(DrawingLayerId.dbr)
// Set the visible property to true or false to control the visibility.
layer?.visible = true
```

## How to Add User Defined DrawingItem(s)

## How to Change the DrawingStyle

Set the style of the highlight overlays with a preset style:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Get the layer first.
DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
// Change the style of the layer.
[layer setDefaultStyle:DSDrawingStyleIdBlueStroke];
```
2. 
```swift
// Get the layer first.
let layer = cameraView.getDrawingLayer(DrawingLayerId.dbr)
// Change the style of the layer.
layer?.setDefaultStyle(DrawingStyleId.blueStroke)
```

Set the style of the highlight overlays with a use defined style:

1. Create colours in the **values/colours.xml** file.

    ```xml
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_200_transparent">#2003DAC5</color>
    ```

2. Create your style with the colour and set to the layer.

    <div class="sample-code-prefix"></div>
    >- Objective-C
    >- Swift
    >
    >1. 
    ```objc
    // Get the layer first.
    DSDrawingLayer *layer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
    // Create a new DrawingStyle via the DrawingStyleManager.
    NSInteger style = [DSDrawingStyleManager createDrawingStyle:UIColor.systemTealColor strokeWidth:1.0 fillColor:[UIColor.systemTealColor colorWithAlphaComponent:0.12] textColor:UIColor.systemTealColor font:UIFontTextStyleBody];
    // Set the newly created DrawingStyle to the layer.
    [layer setDefaultStyle:style];
    ```
    2. 
    ```swift
    // Get the layer first.
    let layer = cameraView.getDrawingLayer(DrawingLayerId.dbr)
    // Create a new DrawingStyle via the DrawingStyleManager.
    let style = DrawingStyleManager.createDrawingStyle(
       UIColor.systemTeal,
       strokeWidth: 1.0,
       fillColor: UIColor.systemTeal.withAlphaComponent(0.12),
       textColor: UIColor.systemTeal,
       font: UIFont.TextStyle.body
    )
    // Set the newly created DrawingStyle to the layer.
    layer?.setDefaultStyle(style)
    ```
