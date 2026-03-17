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

## Hide Barcode Highlight Overlay

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
layer.visible = NO;
```
2. 
```swift
// Get the layer first.
let layer = cameraView.getDrawingLayer(DrawingLayerId.dbr)
// Set the visible property to true or false to control the visibility.
layer?.visible = false
```

## Add User-Define DrawingItem(s)

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSDrawingLayer *barcodeLayer = [self.cameraView getDrawingLayer:DSDrawingLayerIdDBR];
NSMutableArray<DSDrawingItem *> *drawingItemArrayList = [NSMutableArray array];
DSQuadDrawingItem *quadDrawingItem = [[DSQuadDrawingItem alloc] initWithQuad:nil];
[drawingItemArrayList addObject:quadDrawingItem];
[barcodeLayer setDrawingItems:drawingItemArrayList];
// You can also use the append logic if you don't want to clear the previous items.
// [barcodeLayer addDrawingItems:drawingItemArrayList];
```
2. 
```swift
let barcodeLayer = cameraView.getDrawingLayer(DrawingLayerId.dbr)
var drawingItemArrayList: [DrawingItem] = []
let quadDrawingItem = QuadDrawingItem(quad: nil)
drawingItemArrayList.append(quadDrawingItem)
barcodeLayer?.setDrawingItems(drawingItemArrayList)
// You can also use the append logic if you don't want to clear the previous items.
// barcodeLayer?.addDrawingItems(drawingItemArrayList)
```

## How to Change the DrawingStyle

### Use Preset Styles

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

### Use User Defined Styles

Set the style of the highlight overlays with a user defined style:

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
let style = DrawingStyleManager.createDrawingStyle(UIColor.systemTeal, strokeWidth: 1.0, fillColor: UIColor.systemTeal.withAlphaComponent(0.12), textColor: UIColor.systemTeal, font: UIFont.TextStyle.body)
// Set the newly created DrawingStyle to the layer.
layer?.setDefaultStyle(style)
```
